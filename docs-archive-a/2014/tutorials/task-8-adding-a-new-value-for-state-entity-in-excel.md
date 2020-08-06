---
title: 'Tâche 8 : ajout d’une nouvelle valeur pour l’entité État dans Excel | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a763d76b-06a3-4d51-9614-01fc9fb1c158
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cace99419997e48088420c331a823cdf3639a3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703476"
---
# <a name="task-8-adding-a-new-value-for-state-entity-in-excel"></a><span data-ttu-id="46feb-102">Tâche 8 : Ajout d’une nouvelle valeur pour l’entité État dans Excel</span><span class="sxs-lookup"><span data-stu-id="46feb-102">Task 8: Adding a New Value for State Entity in Excel</span></span>
  <span data-ttu-id="46feb-103">Dans cette tâche, vous allez ajouter une valeur pour l'entité État dans Excel et publier la modification sur le serveur MDS.</span><span class="sxs-lookup"><span data-stu-id="46feb-103">In this task, you add a value for the State entity in Excel and publish the change to the MDS server.</span></span>  
  
1.  <span data-ttu-id="46feb-104">Ajoutez une **feuille de travail** dans Excel en cliquant sur l’onglet nouveau situé en bas.</span><span class="sxs-lookup"><span data-stu-id="46feb-104">Add a **work sheet** in Excel by clicking the new tab at the bottom.</span></span>  
  
     <span data-ttu-id="46feb-105">![Excel - Onglet Nouvelle feuille de calcul](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - Onglet Nouvelle feuille de calcul")</span><span class="sxs-lookup"><span data-stu-id="46feb-105">![Excel - New Worksheet Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - New Worksheet Tab")</span></span>  
  
2.  <span data-ttu-id="46feb-106">Dans **Excel**, cliquez sur l’onglet **données** de référence dans le menu, puis sur **afficher l’Explorateur** sur le ruban.</span><span class="sxs-lookup"><span data-stu-id="46feb-106">In **Excel**, click the **Master Data** tab on the menu, and then click **Show Explorer** on the ribbon.</span></span>  
  
3.  <span data-ttu-id="46feb-107">Dans le **Explorateur de données maître**, sélectionnez **Suppliers** pour **Model**.</span><span class="sxs-lookup"><span data-stu-id="46feb-107">In the **Master Data Explorer**, select **Suppliers** for **Model**.</span></span> <span data-ttu-id="46feb-108">Vous devez voir deux entités : **Supplier** et **State** dans la liste d’entités.</span><span class="sxs-lookup"><span data-stu-id="46feb-108">You should see two entities: **Supplier** and **State** in the entity list.</span></span>  
  
4.  <span data-ttu-id="46feb-109">Double-cliquez sur **État** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="46feb-109">Double-click **State** in the list.</span></span> <span data-ttu-id="46feb-110">Tous les membres de l’entité **État** de MDS doivent être affichés dans la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="46feb-110">All the members of the **State** entity from MDS should be displayed in the worksheet.</span></span>  
  
5.  <span data-ttu-id="46feb-111">À présent, ajoutez une ligne à la fin avec les valeurs suivantes : **Caroline du Nord** pour **nom** et **NC** pour le **code**.</span><span class="sxs-lookup"><span data-stu-id="46feb-111">Now, add a row at the end with the following values: **North Carolina** for **Name** and **NC** for **Code**.</span></span> <span data-ttu-id="46feb-112">Les codes de couleur différencient tous les nouveaux enregistrements, ou les enregistrements mis à jour, des autres enregistrements.</span><span class="sxs-lookup"><span data-stu-id="46feb-112">The color coding differentiates any new/updated records from the other records.</span></span>  
  
     <span data-ttu-id="46feb-113">![Excel - Ajouter North Carolina aux États](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Ajouter North Carolina aux États")</span><span class="sxs-lookup"><span data-stu-id="46feb-113">![Excel - Add North Carolina to States](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Add North Carolina to States")</span></span>  
  
6.  <span data-ttu-id="46feb-114">Cliquez sur **publier** sur le ruban pour publier la modification dans MDS.</span><span class="sxs-lookup"><span data-stu-id="46feb-114">Click **Publish** on the ribbon to publish the change to MDS.</span></span>  
  
     <span data-ttu-id="46feb-115">![Excel - Bouton Publier dans l'onglet des données de référence](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Bouton Publier dans l'onglet des données de référence")</span><span class="sxs-lookup"><span data-stu-id="46feb-115">![Excel - Publish Button on Master Data Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Publish Button on Master Data Tab")</span></span>  
  
7.  <span data-ttu-id="46feb-116">Dans la boîte de dialogue **publier et annoter** , Notez que l’option **utiliser la même annotation pour toutes les modifications** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="46feb-116">On the **Publish and Annotate** dialog box, notice that the **Use same annotation for all changes** is selected.</span></span> <span data-ttu-id="46feb-117">Vous pouvez entrer ici une annotation unique pour toutes les modifications apportées.</span><span class="sxs-lookup"><span data-stu-id="46feb-117">You can enter a single annotation for all the changes here.</span></span>  
  
8.  <span data-ttu-id="46feb-118">Sélectionnez l’option **vérifier les modifications et fournir des annotations individuellement** pour fournir une annotation pour chaque modification (dans ce cas, une seule).</span><span class="sxs-lookup"><span data-stu-id="46feb-118">Select **Review changes and provide annotations individually** option to provide annotation for each change (in this case, only one).</span></span>  
  
     <span data-ttu-id="46feb-119">![Excel - Boîte de dialogue Publier et annoter](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Boîte de dialogue Publier et annoter")</span><span class="sxs-lookup"><span data-stu-id="46feb-119">![Excel - Publish and Annotate Dialog Box](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Publish and Annotate Dialog Box")</span></span>  
  
9. <span data-ttu-id="46feb-120">Cliquez sur **publier** pour publier des données sur MDS.</span><span class="sxs-lookup"><span data-stu-id="46feb-120">Click **Publish** to publish data to MDS.</span></span>  
  
10. <span data-ttu-id="46feb-121">Notez que le **codage en couleurs** pour la ligne avec **Caroline du Nord** comme **État** est le même que pour les autres enregistrements maintenant.</span><span class="sxs-lookup"><span data-stu-id="46feb-121">Notice that **color coding** for the row with **North Carolina** as the **State** is same as other records now.</span></span>  
  
11. <span data-ttu-id="46feb-122">**Facultatif :** Vérifiez que le nouveau membre (NC) est ajouté à l’entité **État** à l’aide de l' **explorateur** dans le **Data Manager maître**.</span><span class="sxs-lookup"><span data-stu-id="46feb-122">**Optional:** Verify that the new member (NC) is added to the **State** entity by using the **Explorer** in **Master Data Manager**.</span></span>  
  
12. <span data-ttu-id="46feb-123">Dans Excel, cliquez avec le bouton droit sur la feuille de calcul **État** en bas, puis cliquez sur **supprimer** pour supprimer la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="46feb-123">In Excel, right-click the **State** worksheet at the bottom, and click **Delete** to delete the worksheet.</span></span> <span data-ttu-id="46feb-124">La suppression de la feuille de calcul ne supprime aucune donnée dans le serveur MDS.</span><span class="sxs-lookup"><span data-stu-id="46feb-124">Deleting the worksheet does not delete any data from the MDS server.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="46feb-125">étape suivante</span><span class="sxs-lookup"><span data-stu-id="46feb-125">Next Step</span></span>  
 [<span data-ttu-id="46feb-126">Tâche 9 : Création d’une hiérarchie dérivée à l’aide de Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="46feb-126">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>](../../2014/tutorials/task-9-creating-a-derived-hierarchy-using-master-data-manager.md)  
  
  
