---
title: Exécution de procédures stockées (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [OLE DB], executing
- OLE DB, stored procedures
- SQL Server Native Client OLE DB provider, stored procedures
ms.assetid: c77d9be9-2176-4438-8c7a-04b63ebece08
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e6ce951f343002feea5aa793d0cc2092422b819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706375"
---
# <a name="running-stored-procedures-ole-db"></a><span data-ttu-id="c581b-102">Exécution de procédures stockées (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="c581b-102">Running Stored Procedures (OLE DB)</span></span>
  <span data-ttu-id="c581b-103">Lorsque vous exécutez des instructions, appeler une procédure stockée sur la source de données (au lieu d'exécuter ou de préparer directement une instruction dans l'application cliente) peut fournir :</span><span class="sxs-lookup"><span data-stu-id="c581b-103">When executing statements, calling a stored procedure on the data source (instead of executing or preparing a statement in the client application directly) can provide:</span></span>  
  
-   <span data-ttu-id="c581b-104">des performances accrues ;</span><span class="sxs-lookup"><span data-stu-id="c581b-104">Higher performance.</span></span>  
  
-   <span data-ttu-id="c581b-105">une charge réseau réduite ;</span><span class="sxs-lookup"><span data-stu-id="c581b-105">Reduced network overhead.</span></span>  
  
-   <span data-ttu-id="c581b-106">une cohérence améliorée ;</span><span class="sxs-lookup"><span data-stu-id="c581b-106">Better consistency.</span></span>  
  
-   <span data-ttu-id="c581b-107">une précision améliorée ;</span><span class="sxs-lookup"><span data-stu-id="c581b-107">Better accuracy.</span></span>  
  
-   <span data-ttu-id="c581b-108">des fonctionnalités supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c581b-108">Added functionality.</span></span>  
  
 <span data-ttu-id="c581b-109">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client prend en charge trois des mécanismes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilisés par les procédures stockées pour retourner les données :</span><span class="sxs-lookup"><span data-stu-id="c581b-109">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports three of the mechanisms that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stored procedures use to return data:</span></span>  
  
-   <span data-ttu-id="c581b-110">Chaque instruction SELECT dans la procédure génère un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="c581b-110">Every SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="c581b-111">La procédure peut retourner des données par l'intermédiaire de paramètres de sortie.</span><span class="sxs-lookup"><span data-stu-id="c581b-111">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="c581b-112">La procédure peut avoir un code de retour de type entier.</span><span class="sxs-lookup"><span data-stu-id="c581b-112">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="c581b-113">L'application doit être en mesure de gérer toutes ces sorties provenant de procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="c581b-113">The application must be able to handle all of these outputs from stored procedures.</span></span>  
  
 <span data-ttu-id="c581b-114">Des fournisseurs OLE DB différents retournent des paramètres de sortie et des valeurs de retour à des moments différents pendant le traitement des résultats.</span><span class="sxs-lookup"><span data-stu-id="c581b-114">Different OLE DB providers return output parameters and return values at different times during result processing.</span></span> <span data-ttu-id="c581b-115">Dans le cas du [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client, les paramètres de sortie et les codes de retour ne sont pas fournis tant que le consommateur n’a pas récupéré ou annulé les jeux de résultats retournés par la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="c581b-115">In case of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the output parameters and return codes are not supplied until after the consumer has retrieved or canceled the result sets returned by the stored procedure.</span></span> <span data-ttu-id="c581b-116">Les codes de retour et les paramètres de sortie sont retournés dans le dernier paquet TDS provenant du serveur.</span><span class="sxs-lookup"><span data-stu-id="c581b-116">The return codes and the output parameters are returned in the last TDS packet from the server.</span></span>  
  
 <span data-ttu-id="c581b-117">Les fournisseurs utilisent la propriété DBPROP_OUTPUTPARAMETERAVAILABILITY pour signaler quand les paramètres de sortie et les valeurs de retour sont retournés.</span><span class="sxs-lookup"><span data-stu-id="c581b-117">Providers use the DBPROP_OUTPUTPARAMETERAVAILABILITY property to report when it returns output parameters and return values.</span></span> <span data-ttu-id="c581b-118">Cette propriété figure dans le jeu de propriétés DBPROPSET_DATASOURCEINFO.</span><span class="sxs-lookup"><span data-stu-id="c581b-118">This property is in the DBPROPSET_DATASOURCEINFO property set.</span></span>  
  
 <span data-ttu-id="c581b-119">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client définit la propriété DBPROP_OUTPUTPARAMETERAVAILABILITY sur DBPROPVAL_OA_ATROWRELEASE pour indiquer que les codes de retour et les paramètres de sortie ne sont pas retournés tant que le jeu de résultats n’est pas traité ou libéré.</span><span class="sxs-lookup"><span data-stu-id="c581b-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets the DBPROP_OUTPUTPARAMETERAVAILABILITY property to DBPROPVAL_OA_ATROWRELEASE to indicate that return codes and output parameters are not returned until the result set is processed or released.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c581b-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c581b-120">See Also</span></span>  
 [<span data-ttu-id="c581b-121">Procédures stockées</span><span class="sxs-lookup"><span data-stu-id="c581b-121">Stored Procedures</span></span>](stored-procedures.md)  
  
  
