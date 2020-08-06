---
title: Gestionnaire de connexions ADO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ADO
- connection managers [Integration Services], ADO
- ADO connection manager [Integration Services]
ms.assetid: 490418bc-5ef1-41b8-a9c8-de38aa96e0f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb4b667733f81eebbaf2b6a2ab9b205c09fe2c66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613101"
---
# <a name="ado-connection-manager"></a><span data-ttu-id="39fb3-102">Gestionnaire de connexions ADO</span><span class="sxs-lookup"><span data-stu-id="39fb3-102">ADO Connection Manager</span></span>
  <span data-ttu-id="39fb3-103">Un gestionnaire de connexions ADO permet à un package de se connecter à des objets ADO (ActiveX Data Objects), comme un recordset.</span><span class="sxs-lookup"><span data-stu-id="39fb3-103">An ADO connection manager enables a package to connect to ActiveX Data Objects (ADO) objects, such as a recordset.</span></span> <span data-ttu-id="39fb3-104">Ce gestionnaire de connexions est généralement utilisé dans les tâches personnalisées écrites dans une version antérieure d’un langage comme Microsoft Visual Basic 6.0 ou dans les tâches personnalisées qui font partie d’une application existante utilisant ADO pour se connecter à une source de données.</span><span class="sxs-lookup"><span data-stu-id="39fb3-104">This connection manager is typically used in custom tasks written in an earlier version of a language, such as Microsoft Visual Basic 6.0, or in custom tasks that are part of an existing application that uses ADO to connect to a data source.</span></span>  
  
 <span data-ttu-id="39fb3-105">Lorsque vous ajoutez un gestionnaire de connexions ADO à un package, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera résolu en connexion ADO au moment de l’exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la `Connections` collection sur le package.</span><span class="sxs-lookup"><span data-stu-id="39fb3-105">When you add an ADO connection manager to a package, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an ADO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="39fb3-106">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `ADO`.</span><span class="sxs-lookup"><span data-stu-id="39fb3-106">The `ConnectionManagerType` property of the connection manager is set to `ADO`.</span></span>  
  
## <a name="troubleshooting-the-ado-connection-manager"></a><span data-ttu-id="39fb3-107">Résolution des problèmes liés au gestionnaire de connexions ADO</span><span class="sxs-lookup"><span data-stu-id="39fb3-107">Troubleshooting the ADO Connection Manager</span></span>  
 <span data-ttu-id="39fb3-108">Lors de la lecture par un gestionnaire de connexions ADO, certains types de données de date [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] génèrent les résultats présentés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="39fb3-108">When being read by an ADO connection manager, certain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date data types will generate the results shown in the following table.</span></span>  
  
|<span data-ttu-id="39fb3-109">Type de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="39fb3-109">SQL Server Data type</span></span>|<span data-ttu-id="39fb3-110">Résultats</span><span class="sxs-lookup"><span data-stu-id="39fb3-110">Result</span></span>|  
|--------------------------|------------|  
|<span data-ttu-id="39fb3-111">`time`, `datetimeoffset`</span><span class="sxs-lookup"><span data-stu-id="39fb3-111">`time`, `datetimeoffset`</span></span>|<span data-ttu-id="39fb3-112">Le package échoue s'il n'utilise pas de commandes SQL paramétrables.</span><span class="sxs-lookup"><span data-stu-id="39fb3-112">The package fails unless the package uses parameterized SQL commands.</span></span> <span data-ttu-id="39fb3-113">Pour utiliser des commandes SQL paramétrables, utilisez la tâche d'exécution SQL dans votre package.</span><span class="sxs-lookup"><span data-stu-id="39fb3-113">To use parameterized SQL commands, use the Execute SQL Task in your package.</span></span> <span data-ttu-id="39fb3-114">Pour plus d’informations, consultez [Tâche d’exécution de requêtes SQL](../control-flow/execute-sql-task.md) et [Paramètres et codes de retour dans la tâche d’exécution SQL](../parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="39fb3-114">For more information, see [Execute SQL Task](../control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>|  
|`datetime2`|<span data-ttu-id="39fb3-115">Le gestionnaire de connexions ADO tronque les millisecondes.</span><span class="sxs-lookup"><span data-stu-id="39fb3-115">The ADO connection manager truncates the millisecond value.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="39fb3-116">Pour plus d’informations sur les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et leur mappage aux types de données [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], consultez [Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) et [Types de données d’Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="39fb3-116">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and how they map to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) and [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="configuring-the-ado-connection-manager"></a><span data-ttu-id="39fb3-117">Configuration du gestionnaire de connexions ADO</span><span class="sxs-lookup"><span data-stu-id="39fb3-117">Configuring the ADO Connection Manager</span></span>  
 <span data-ttu-id="39fb3-118">Vous pouvez configurer un gestionnaire de connexions ADO de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="39fb3-118">You can configure an ADO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="39fb3-119">Indiquez une chaîne de connexion spécifique configurée pour répondre aux besoins du fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="39fb3-119">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="39fb3-120">Selon le fournisseur, incluez le nom de la source de données à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="39fb3-120">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="39fb3-121">Fournissez les informations d'identification de sécurité nécessaires selon le fournisseur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="39fb3-121">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="39fb3-122">Indiquez si la connexion créée à partir du gestionnaire de connexions est conservée au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="39fb3-122">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="39fb3-123">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="39fb3-123">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="39fb3-124">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="39fb3-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="39fb3-125">Configurer le gestionnaire de connexions OLE DB</span><span class="sxs-lookup"><span data-stu-id="39fb3-125">Configure OLE DB Connection Manager</span></span>](ole-db-connection-manager.md)  
  
 <span data-ttu-id="39fb3-126">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="39fb3-126">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39fb3-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39fb3-127">See Also</span></span>  
 [<span data-ttu-id="39fb3-128">Connexions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="39fb3-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
