---
title: Création d’une application de fournisseur d’OLE DB SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, application creation
- applications [SQL Server Native Client]
- OLE DB, creating applications
ms.assetid: f3ae6815-f32d-4913-a1a2-2ba2f20cfd88
author: rothja
ms.author: jroth
ms.openlocfilehash: a661f23cdacc4b581dadbe7625cb6e2ea318857f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698123"
---
# <a name="creating-a-sql-server-native-client-ole-db-provider-application"></a><span data-ttu-id="6890b-102">Création d'une application de fournisseur OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="6890b-102">Creating a SQL Server Native Client OLE DB Provider Application</span></span>
  <span data-ttu-id="6890b-103">La création d’une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] application de fournisseur OLE DB Native Client implique les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="6890b-103">Creating a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider application involves these steps:</span></span>  
  
1.  <span data-ttu-id="6890b-104">Établissement d'une connexion à une source de données.</span><span class="sxs-lookup"><span data-stu-id="6890b-104">Establishing a connection to a data source.</span></span>  
  
2.  <span data-ttu-id="6890b-105">Exécution d'une commande.</span><span class="sxs-lookup"><span data-stu-id="6890b-105">Executing a command.</span></span>  
  
3.  <span data-ttu-id="6890b-106">Traitement des résultats.</span><span class="sxs-lookup"><span data-stu-id="6890b-106">Processing the results.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6890b-107">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="6890b-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="6890b-108">Si l'authentification Windows n'est pas disponible, invitez les utilisateurs à entrer leurs informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="6890b-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="6890b-109">Évitez de stocker ces informations dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="6890b-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="6890b-110">Si vous devez rendre les informations d’identification persistantes, chiffrez-les avec [l’API de chiffrement Win32 cryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504).</span><span class="sxs-lookup"><span data-stu-id="6890b-110">If you must persist credentials, you should encrypt them with [the Win32 cryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6890b-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6890b-111">In This Section</span></span>  
  
-   [<span data-ttu-id="6890b-112">Établissement d'une connexion à une source de données</span><span class="sxs-lookup"><span data-stu-id="6890b-112">Establishing a Connection to a Data Source</span></span>](establishing-a-connection-to-a-data-source.md)  
  
-   [<span data-ttu-id="6890b-113">Exécution d'une commande</span><span class="sxs-lookup"><span data-stu-id="6890b-113">Executing a Command</span></span>](executing-a-command.md)  
  
-   [<span data-ttu-id="6890b-114">Traitement des résultats</span><span class="sxs-lookup"><span data-stu-id="6890b-114">Processing Results</span></span>](processing-results.md)  
  
-   [<span data-ttu-id="6890b-115">À propos des propriétés OLE DB</span><span class="sxs-lookup"><span data-stu-id="6890b-115">About OLE DB Properties</span></span>](about-ole-db-properties.md)  
  
-   [<span data-ttu-id="6890b-116">Utilisation de la clause OUTPUT avec OLE DB dans SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="6890b-116">Using the OUTPUT Clause with OLE DB in SQL Server Native Client</span></span>](using-the-output-clause-with-ole-db-in-sql-server-native-client.md)  
  
## <a name="see-also"></a><span data-ttu-id="6890b-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6890b-117">See Also</span></span>  
 [<span data-ttu-id="6890b-118">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6890b-118">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
