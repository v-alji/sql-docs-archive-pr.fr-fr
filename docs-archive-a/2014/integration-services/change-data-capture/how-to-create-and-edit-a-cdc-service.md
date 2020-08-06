---
title: Guide pratique pour créer et modifier un service CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1b3d47a5-dc89-482d-bbc7-fff04f194c43
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d90534b475901b08fcd2e09acdc0f7976f0fb6e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695979"
---
# <a name="how-to-create-and-edit-a-cdc-service"></a><span data-ttu-id="c4647-102">Procédure : créer et modifier un service de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="c4647-102">How to Create and Edit a CDC Service</span></span>
  <span data-ttu-id="c4647-103">Ces procédures décrivent comment créer et modifier un service de capture de données modifiées Oracle dans la console de configuration du service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="c4647-103">These procedures describe how to create and edit a new Oracle CDC Service from the CDC Service Configuration Console.</span></span>  
  
 <span data-ttu-id="c4647-104">Cette procédure requiert un utilisateur Windows avec des privilèges d'administrateur sur l'ordinateur sur lequel le service de capture de données modifiées Oracle est configuré.</span><span class="sxs-lookup"><span data-stu-id="c4647-104">This procedure requires a Windows user with administrator privileges on the computer where the Oracle CDC service is configured.</span></span>  
  
### <a name="to-create-a-new-cdc-service"></a><span data-ttu-id="c4647-105">Pour créer un service de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="c4647-105">To create a new CDC service</span></span>  
  
1.  <span data-ttu-id="c4647-106">Dans le menu **Démarrer** , sélectionnez **Configuration du service de capture de données modifiées pour Oracle**.</span><span class="sxs-lookup"><span data-stu-id="c4647-106">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="c4647-107">Dans le volet gauche, cliquez avec le bouton droit sur Services de capture de données modifiées locaux, puis sélectionnez Nouveau service.</span><span class="sxs-lookup"><span data-stu-id="c4647-107">From the left pane, right click Local CDC Services and select New Service</span></span>  
  
     <span data-ttu-id="c4647-108">Vous pouvez également cliquer sur **Nouveau service** dans le volet **Actions** .</span><span class="sxs-lookup"><span data-stu-id="c4647-108">You can also click **New Service** from the **Actions** pane.</span></span>  
  
3.  <span data-ttu-id="c4647-109">Tapez ou entrez les informations nécessaires dans la boîte de dialogue Nouveau service de capture de données modifiées Oracle.</span><span class="sxs-lookup"><span data-stu-id="c4647-109">Type or enter the required information in the New Oracle CDC Service dialog box.</span></span> <span data-ttu-id="c4647-110">Pour plus d'informations sur la façon d'entrer des informations dans la boîte de dialogue Nouveau service de capture de données modifiées Oracle, consultez [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) .</span><span class="sxs-lookup"><span data-stu-id="c4647-110">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the New Oracle CDC Service dialog box.</span></span>  
  
     <span data-ttu-id="c4647-111">La connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifiée dans la boîte de dialogue Nouveau service de capture de données modifiées Oracle est utilisée par le service de capture de données modifiées Oracle lorsqu'il s'exécute.</span><span class="sxs-lookup"><span data-stu-id="c4647-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login provided in the New Oracle CDC Service dialog box is used by the Oracle CDC Service when the service runs.</span></span> <span data-ttu-id="c4647-112">Cette connexion doit être membre du rôle serveur fixe public ; aucun autre privilège n'est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c4647-112">This login only needs to be a member of the public fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="c4647-113">Une fois que de nouvelles instances Oracle CDC sont ajoutées, cette connexion a un accès **db_owner** aux bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC.</span><span class="sxs-lookup"><span data-stu-id="c4647-113">Once new Oracle CDC Instances are added, that login receives **db_owner** access to the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC databases.</span></span>  
  
4.  <span data-ttu-id="c4647-114">Lorsque vous avez terminé d'entrer les informations nécessaires, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4647-114">When you finish entering the required information, click **OK**.</span></span>  
  
     <span data-ttu-id="c4647-115">Pour créer la définition de service Windows de capture de données modifiées Oracle, le programme doit disposer d'un accès de mise à jour à la base de données MSXDBCDC dans l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associée.</span><span class="sxs-lookup"><span data-stu-id="c4647-115">To create the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="c4647-116">Lorsque vous cliquez sur **OK**, une boîte de dialogue vous invite à entrer une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec un accès de mise à jour à la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="c4647-116">When you click **OK**, a dialog box prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
     <span data-ttu-id="c4647-117">Pour plus d'informations sur les données que vous devez taper dans la boîte de dialogue Connexion à SQL Server, consultez [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c4647-117">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="c4647-118">Cliquez sur **OK** pour fermer la boîte de dialogue Nouveau service de capture de données modifiées Oracle.</span><span class="sxs-lookup"><span data-stu-id="c4647-118">Click **OK** to close the New Oracle CDC Service dialog box.</span></span>  
  
### <a name="to-edit-a-cdc-service"></a><span data-ttu-id="c4647-119">Pour modifier un service de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="c4647-119">To edit a CDC service</span></span>  
  
1.  <span data-ttu-id="c4647-120">Dans le menu **Démarrer** , sélectionnez **Configuration du service de capture de données modifiées pour Oracle**.</span><span class="sxs-lookup"><span data-stu-id="c4647-120">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="c4647-121">Dans le volet gauche, sélectionnez **Services de capture de données modifiées locaux** , cliquez avec le bouton droit sur le service local que vous souhaitez modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c4647-121">From the left pane, select **Local CDC Services** then right-click the local service you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="c4647-122">Vous pouvez également sélectionner le service que vous utilisez dans le volet central, puis dans le volet **Actions** , cliquer sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c4647-122">You can also select the service you are working with in the middle and then from the **Actions** pane, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c4647-123">Tapez ou entrez les informations nécessaires dans la boîte de dialogue de propriétés du service de capture de données modifiées Oracle.</span><span class="sxs-lookup"><span data-stu-id="c4647-123">Type or enter the required information in the CDC Service Properties dialog box.</span></span> <span data-ttu-id="c4647-124">Pour plus d'informations sur la façon d'entrer des informations dans la boîte de dialogue de propriétés du service de capture de données modifiées Oracle, consultez [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) .</span><span class="sxs-lookup"><span data-stu-id="c4647-124">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the CDC Service Properties dialog box.</span></span>  
  
4.  <span data-ttu-id="c4647-125">Lorsque vous avez terminé d'entrer les informations nécessaires, cliquez sur **OK**; la boîte de dialogue Connexion à SQL Server s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="c4647-125">When you finish entering the required information, Click **OK**, the Connect to SQL Server dialog box opens.</span></span>  
  
     <span data-ttu-id="c4647-126">Lorsqu'une connexion sans autorisation d'écriture sur la base de données MSXDBDCDC tente de créer une instance Oracle CDC un message d'erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="c4647-126">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="c4647-127">Cliquez sur **OK** dans cette boîte de dialogue pour afficher la boîte de dialogue Connexion à SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c4647-127">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span> <span data-ttu-id="c4647-128">Dans cette boîte de dialogue, vous devez entrer les informations d’identification pour une connexion qui dispose de l’autorisation en écriture sur la base de données MSXDBCDC, telle que le rôle de base de données **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c4647-128">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role.</span></span>  
  
     <span data-ttu-id="c4647-129">Pour plus d'informations sur les données que vous devez taper dans la boîte de dialogue Connexion à SQL Server, consultez [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c4647-129">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="c4647-130">Cliquez sur **OK** dans la boîte de dialogue Connexion à Oracle.</span><span class="sxs-lookup"><span data-stu-id="c4647-130">Click **OK** in the Connect to Oracle dialog box.</span></span> <span data-ttu-id="c4647-131">Les deux boîtes de dialogue se ferment et le service est mis à jour et inscrit.</span><span class="sxs-lookup"><span data-stu-id="c4647-131">Both dialog boxes close and the service is updated and registered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4647-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4647-132">See Also</span></span>  
 <span data-ttu-id="c4647-133">[Concepteur de capture de données modifiées pour Oracle par Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="c4647-133">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="c4647-134">Créer et modifier un service CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="c4647-134">Create and Edit an Oracle CDC Service</span></span>](create-and-edit-an-oracle-cdc-service.md)  
  
  
