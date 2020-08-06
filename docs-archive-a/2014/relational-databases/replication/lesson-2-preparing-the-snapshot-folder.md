---
title: 'Leçon 2 : Préparation du dossier d’instantanés | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f286cde9-c0d0-43ef-b7ba-53c3cbb8906c
author: rothja
ms.author: jroth
ms.openlocfilehash: 5d98c7433d0bd50504f20f7f576fcf0b20154c81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707383"
---
# <a name="lesson-2-preparing-the-snapshot-folder"></a><span data-ttu-id="7dd19-102">Leçon 2 : Préparation du dossier d'instantanés</span><span class="sxs-lookup"><span data-stu-id="7dd19-102">Lesson 2: Preparing the Snapshot Folder</span></span>
  <span data-ttu-id="7dd19-103">Dans cette leçon, vous allez apprendre à configurer le dossier d'instantanés utilisé pour créer et stocker l'instantané des publications.</span><span class="sxs-lookup"><span data-stu-id="7dd19-103">In this lesson, you will learn to configure the snapshot folder that is used to create and store the publication snapshot.</span></span>  
  
### <a name="to-create-a-share-for-the-snapshot-folder-and-assign-permissions"></a><span data-ttu-id="7dd19-104">Pour créer un partage pour le dossier d'instantanés et attribuer les autorisations</span><span class="sxs-lookup"><span data-stu-id="7dd19-104">To create a share for the snapshot folder and assign permissions</span></span>  
  
1.  <span data-ttu-id="7dd19-105">Dans l'Explorateur Windows, accédez au dossier des données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7dd19-105">In Windows Explorer, navigate to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data folder.</span></span> <span data-ttu-id="7dd19-106">L'emplacement par défaut est : C:\Program Files\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="7dd19-106">The default location is C:\Program Files\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="7dd19-107">Créez un dossier nommé **repldata**.</span><span class="sxs-lookup"><span data-stu-id="7dd19-107">Create a new folder named **repldata**.</span></span>  
  
3.  <span data-ttu-id="7dd19-108">Cliquez avec le bouton droit sur ce dossier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7dd19-108">Right-click this folder and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7dd19-109">Sous l’onglet **Partage** de la boîte de dialogue **Propriétés de repldata** , cliquez sur **Partager**.</span><span class="sxs-lookup"><span data-stu-id="7dd19-109">On the **Sharing** tab in the **repldata Properties** dialog box, click **Share**.</span></span>  
  
5.  <span data-ttu-id="7dd19-110">Dans la boîte de dialogue **Partage de fichiers** , cliquez sur **Partager**, puis sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="7dd19-110">In the **File Sharing** dialog box, click **Share**, and then click **Done**.</span></span>  
  
6.  <span data-ttu-id="7dd19-111">Sur l'onglet **Sécurité** , cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7dd19-111">On the **Security** tab, click **Edit**.</span></span>  
  
7.  <span data-ttu-id="7dd19-112">Dans la boîte de dialogue **Autorisations** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="7dd19-112">In the **Permissions** dialog box, click **Add.**</span></span> <span data-ttu-id="7dd19-113">Dans la zone de texte **Sélectionner l’utilisateur, les ordinateurs, le compte de service ou les groupes** , tapez le nom du compte agent d’instantané créé au cours de la leçon 1, sous la forme \<_Machine_Name> _**\ repl_snapshot**, où \<*Machine_Name> \* est le nom du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="7dd19-113">In the **Select User, Computers, Service Account, or Groups** text box, type the name of the Snapshot Agent account created in Lesson 1, as \<_Machine_Name>_**\repl_snapshot**, where \<*Machine_Name>\* is the name of the Publisher.</span></span> <span data-ttu-id="7dd19-114">Cliquez sur **Vérifier les noms**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7dd19-114">Click **Check Names**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="7dd19-115">Répétez l’étape précédente pour ajouter des autorisations pour le agent de distribution, sous la forme \<_Machine_Name> _ **\ repl_distribution**, et \<_Machine_Name> pour le agent de fusion en tant que _ **\ repl_merge**.</span><span class="sxs-lookup"><span data-stu-id="7dd19-115">Repeat the previous step to add permissions for the Distribution Agent, as \<_Machine_Name>_**\repl_distribution**, and for the Merge Agent as \<_Machine_Name>_**\repl_merge**.</span></span>  
  
9. <span data-ttu-id="7dd19-116">Vérifiez que les autorisations suivantes sont accordées :</span><span class="sxs-lookup"><span data-stu-id="7dd19-116">Verify the following permissions are allowed:</span></span>  
  
    -   <span data-ttu-id="7dd19-117">repl_snapshot - Contrôle total</span><span class="sxs-lookup"><span data-stu-id="7dd19-117">repl_snapshot - Full Control</span></span>  
  
    -   <span data-ttu-id="7dd19-118">repl_distribution - Lecture</span><span class="sxs-lookup"><span data-stu-id="7dd19-118">repl_distribution - Read</span></span>  
  
    -   <span data-ttu-id="7dd19-119">repl_merge - Lecture</span><span class="sxs-lookup"><span data-stu-id="7dd19-119">repl_merge - Read</span></span>  
  
10. <span data-ttu-id="7dd19-120">Cliquez sur **OK** pour fermer la boîte de dialogue **Propriétés de repldata** et créer le partage repldata.</span><span class="sxs-lookup"><span data-stu-id="7dd19-120">Click **OK** to close the **repldata Properties** dialog box and create the repldata share.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7dd19-121">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="7dd19-121">Next Steps</span></span>  
 <span data-ttu-id="7dd19-122">Vous avez configuré avec succès le partage du dossier d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="7dd19-122">You have successfully configured the share for the snapshot folder.</span></span> <span data-ttu-id="7dd19-123">Ensuite, vous allez configurer la distribution.</span><span class="sxs-lookup"><span data-stu-id="7dd19-123">Next, you will configure distribution.</span></span> <span data-ttu-id="7dd19-124">Consultez [Leçon 3 : Configuration de la distribution](lesson-3-configuring-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="7dd19-124">See [Lesson 3: Configuring Distribution](lesson-3-configuring-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd19-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7dd19-125">See Also</span></span>  
 [<span data-ttu-id="7dd19-126">Sécuriser le dossier d’instantanés</span><span class="sxs-lookup"><span data-stu-id="7dd19-126">Secure the Snapshot Folder</span></span>](security/secure-the-snapshot-folder.md)  
  
  
