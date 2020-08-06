---
title: Rapprocher un schéma de base de données d’une base de données modifiée (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- updating diagram to match database
- reconciling database diagrams
- diagrams [SQL Server], reconciling changes
- updating database to match diagram
- database diagrams [SQL Server], reconciling changes
ms.assetid: eda8dea2-eedd-43a7-85aa-92bd97783b5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e5e5127ab613a6f791919a98899e40caa2ddac20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697336"
---
# <a name="reconcile-a-database-diagram-with-a-modified-database-visual-database-tools"></a><span data-ttu-id="632b3-102">Rapprocher un diagramme de base de données et une base de données modifiée (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="632b3-102">Reconcile a Database Diagram with a Modified Database (Visual Database Tools)</span></span>
  <span data-ttu-id="632b3-103">Vous enregistrez votre diagramme de base de données lorsque vous êtes prêt à mettre à jour la base de données par rapport à ce diagramme.</span><span class="sxs-lookup"><span data-stu-id="632b3-103">You save your database diagram when you are ready to update the database to match your diagram.</span></span> <span data-ttu-id="632b3-104">Toutefois, si d'autres utilisateurs ont mis à jour la base de données depuis l'ouverture de votre schéma, leurs modifications risquent d'avoir une incidence sur le schéma et vice versa.</span><span class="sxs-lookup"><span data-stu-id="632b3-104">However, if other users have updated the database since you opened your diagram, their changes might affect your diagram and vice versa.</span></span>  
  
 <span data-ttu-id="632b3-105">L'enregistrement de votre schéma provoquera un rapprochement entre votre base de données et votre schéma en écrasant les autres modifications des utilisateurs, de telle sorte que votre base de données corresponde à votre schéma.</span><span class="sxs-lookup"><span data-stu-id="632b3-105">Saving your diagram will reconcile the database with your diagram by overwriting other users' changes so that the database will match your diagram.</span></span>  
  
### <a name="to-update-a-database-to-match-your-diagram"></a><span data-ttu-id="632b3-106">Pour mettre à jour une base de données afin qu'elle corresponde à votre schéma</span><span class="sxs-lookup"><span data-stu-id="632b3-106">To update a database to match your diagram</span></span>  
  
1.  <span data-ttu-id="632b3-107">Enregistrez votre diagramme de base de données.</span><span class="sxs-lookup"><span data-stu-id="632b3-107">Save your database diagram.</span></span>  
  
     <span data-ttu-id="632b3-108">Si vous n’avez pas encore enregistré votre diagramme, tapez le nom que vous voulez lui attribuer dans la boîte de dialogue **Enregistrer un nouveau diagramme de base de données** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="632b3-108">If you have not previously saved your diagram, type a name for the diagram in the **Save New Database Diagram** dialog box and choose **OK**.</span></span>  
  
2.  <span data-ttu-id="632b3-109">La boîte de dialogue **Enregistrer** affiche la liste des tables qui seront affectées quand vous enregistrerez votre schéma.</span><span class="sxs-lookup"><span data-stu-id="632b3-109">The **Save** dialog box lists the tables that will be affected when you save your diagram.</span></span> <span data-ttu-id="632b3-110">Choisissez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="632b3-110">Choose **Yes** to continue.</span></span>  
  
3.  <span data-ttu-id="632b3-111">La boîte de dialogue **Modifications détectées dans la base de données** affiche la liste des objets qui ont changé et qui seront modifiés de façon à correspondre à votre schéma.</span><span class="sxs-lookup"><span data-stu-id="632b3-111">The **Database Changes Detected** dialog box lists the objects that were modified and will be changed to match your diagram.</span></span> <span data-ttu-id="632b3-112">Choisissez **Oui** pour enregistrer le schéma et accepter la liste des changements.</span><span class="sxs-lookup"><span data-stu-id="632b3-112">Choose **Yes** to save the diagram and accept the list of changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="632b3-113">Si votre schéma contient des tables et des colonnes qui ont été supprimées de la base de données, seules leurs définitions sont recréées dans la base de données lorsque vous enregistrez votre schéma.</span><span class="sxs-lookup"><span data-stu-id="632b3-113">If your diagram contains tables and columns that were deleted in the database, only their definitions are recreated in the database when you save your diagram.</span></span> <span data-ttu-id="632b3-114">Ce processus ne restaure pas les données qui existaient dans ces objets avant leur suppression.</span><span class="sxs-lookup"><span data-stu-id="632b3-114">This process does not restore any data that existed in these objects before their deletion.</span></span>  
  
### <a name="to-update-your-diagram-to-match-a-modified-database"></a><span data-ttu-id="632b3-115">Pour mettre à jour votre schéma afin qu'il corresponde à une base de données modifiée</span><span class="sxs-lookup"><span data-stu-id="632b3-115">To update your diagram to match a modified database</span></span>  
  
1.  <span data-ttu-id="632b3-116">Fermez votre schéma sans enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="632b3-116">Close your diagram without saving changes.</span></span>  
  
2.  <span data-ttu-id="632b3-117">Cliquez avec le bouton droit sur le schéma dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="632b3-117">Right-click the diagram in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="632b3-118">Dans le menu contextuel, cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="632b3-118">From the shortcut menu click **Refresh**.</span></span>  
  
4.  <span data-ttu-id="632b3-119">Rouvrez le schéma.</span><span class="sxs-lookup"><span data-stu-id="632b3-119">Reopen the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="632b3-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="632b3-120">See Also</span></span>  
 [<span data-ttu-id="632b3-121">Utiliser des diagrammes de base de données &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="632b3-121">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
