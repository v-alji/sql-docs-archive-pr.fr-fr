---
title: Guide pratique pour gérer un service CDC local | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f9be649-cd93-40c1-bc48-0480106f207c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 437590d4b91f2fc80d5bb8a90251bf0dc7c8e18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694672"
---
# <a name="how-to-manage-a-local-cdc-service"></a><span data-ttu-id="3e702-102">Procédure : gérer un service de capture de données modifiées local</span><span class="sxs-lookup"><span data-stu-id="3e702-102">How to Manage a Local CDC Service</span></span>
  <span data-ttu-id="3e702-103">Cette procédure décrit comment utiliser la console de configuration du service de capture de données modifiées pour gérer des services de capture de données modifiées spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3e702-103">This procedure describes how to use the CDC Service Configuration Console to manage specific CDC services.</span></span>  
  
### <a name="to-manage-a-specific-cdc-service"></a><span data-ttu-id="3e702-104">Pour gérer un service de capture de données modifiées spécifique</span><span class="sxs-lookup"><span data-stu-id="3e702-104">To manage a specific CDC Service</span></span>  
  
1.  <span data-ttu-id="3e702-105">Dans le menu **Démarrer** , sélectionnez **Configuration du service de capture de données modifiées pour Oracle**.</span><span class="sxs-lookup"><span data-stu-id="3e702-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="3e702-106">Dans le volet gauche de la console de configuration du service de capture de données modifiées, développez **Services de capture de données modifiées locaux**.</span><span class="sxs-lookup"><span data-stu-id="3e702-106">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
3.  <span data-ttu-id="3e702-107">Sélectionnez le service de capture de données modifiées à utiliser.</span><span class="sxs-lookup"><span data-stu-id="3e702-107">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="3e702-108">Vous pouvez également cliquer avec le bouton droit sur le service de capture de données modifiées que vous souhaitez utiliser et sélectionner l'action souhaitée.</span><span class="sxs-lookup"><span data-stu-id="3e702-108">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
     <span data-ttu-id="3e702-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="3e702-109">**OR**</span></span>  
  
     <span data-ttu-id="3e702-110">Sélectionnez **Services de capture de données modifiées locaux** dans le volet gauche de la console de configuration du service de capture de données modifiées, puis sélectionnez le service que vous souhaitez utiliser dans la section centrale de la console de configuration du service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="3e702-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console then select the service you want to work with from the middle section of the CDC Service Configuration Console.</span></span>  
  
     <span data-ttu-id="3e702-111">Vous pouvez également cliquer avec le bouton droit sur le service de capture de données modifiées que vous souhaitez utiliser et sélectionner l'action souhaitée.</span><span class="sxs-lookup"><span data-stu-id="3e702-111">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
4.  <span data-ttu-id="3e702-112">Vous pouvez effectuer les tâches suivantes lorsque vous utilisez un service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="3e702-112">You can carry out the following tasks when working with a CDC service.</span></span>  
  
    -   <span data-ttu-id="3e702-113">**Supprimer le service**</span><span class="sxs-lookup"><span data-stu-id="3e702-113">**Delete the service**</span></span>  
  
         <span data-ttu-id="3e702-114">Dans le volet **Actions** à droite de la console de configuration du service de capture de données modifiées, cliquez sur **Supprimer** pour supprimer le service.</span><span class="sxs-lookup"><span data-stu-id="3e702-114">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
         <span data-ttu-id="3e702-115">Vous pouvez également cliquer avec le bouton droit sur le service de capture de données modifiées à supprimer et sélectionner **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="3e702-115">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
         <span data-ttu-id="3e702-116">**Remarque**: si le service est en cours d'exécution lors de sa suppression, il est arrêté avant d'être supprimé.</span><span class="sxs-lookup"><span data-stu-id="3e702-116">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
         <span data-ttu-id="3e702-117">Pour supprimer une définition de service Windows de capture de données modifiées Oracle, le programme doit disposer d'un accès de mise à jour à la base de données MSXDBCDC dans l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associée.</span><span class="sxs-lookup"><span data-stu-id="3e702-117">To delete an Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="3e702-118">Lorsque vous cliquez sur **OK** pour supprimer le service, le programme tente de supprimer l'inscription du service de capture de données modifiées Oracle dans la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="3e702-118">When you click **OK** to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="3e702-119">Si cette opération échoue en raison de l'absence d'autorisations, une boîte de dialogue s'affiche pour inviter l'utilisateur à entrer une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec un accès de mise à jour de la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="3e702-119">If it fails due to lack of permissions, a dialog box is displayed to prompt the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
         <span data-ttu-id="3e702-120">Pour plus d'informations sur les données que vous devez taper dans la boîte de dialogue Connexion à SQL Server, consultez [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) et [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="3e702-120">For information about the data you must enter in the Connect to SQL Server dialog box, see [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) and [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
    -   <span data-ttu-id="3e702-121">**Modifier les propriétés de service de capture de données modifiées**</span><span class="sxs-lookup"><span data-stu-id="3e702-121">**Edit the CDC Service Properties**</span></span>  
  
         <span data-ttu-id="3e702-122">Dans le volet **Actions** à droite de la console de configuration du service de capture de données modifiées, cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3e702-122">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
         <span data-ttu-id="3e702-123">Vous pouvez également cliquer avec le bouton droit sur le service de capture de données modifiées où vous souhaitez modifier les propriétés et sélectionner **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3e702-123">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e702-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e702-124">See Also</span></span>  
 [<span data-ttu-id="3e702-125">Gérer un service CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="3e702-125">Manage an Oracle CDC Service</span></span>](manage-an-oracle-cdc-service.md)  
  
  
