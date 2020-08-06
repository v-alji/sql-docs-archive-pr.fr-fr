---
title: 'Tâche 5 : création d’un attribut basé sur un domaine à partir d’Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 07cbc624-2c6b-4568-96e4-f18663a05d80
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b866478150fb4c06a3c4ea1ee6c227527f963219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700493"
---
# <a name="task-5-creating-a-domain-based-attribute-from-excel"></a><span data-ttu-id="50898-102">Tâche 5 : Création d’un attribut basé sur un domaine à partir d’Excel</span><span class="sxs-lookup"><span data-stu-id="50898-102">Task 5: Creating a Domain-Based Attribute from Excel</span></span>
  <span data-ttu-id="50898-103">Dans cette tâche, vous convertissez l’attribut **State** de l’entité **Supplier** en tant qu' **attribut basé sur un domaine**.</span><span class="sxs-lookup"><span data-stu-id="50898-103">In this task, you convert the **State** attribute of the **Supplier** entity as a **domain-based attribute**.</span></span> <span data-ttu-id="50898-104">Une fois que vous avez configuré l’attribut d’État comme étant basé sur un domaine et que vous l’avez publié sur MDS, une nouvelle entité nommée **État** est créée sur le serveur MDS avec toutes les valeurs de la colonne et l’attribut **État** de l’entité **fournisseur** est rempli avec les valeurs de l’entité **État** .</span><span class="sxs-lookup"><span data-stu-id="50898-104">After you configure the State attribute to be a domain-based one and publish it to MDS, a new entity named **State** will be created on MDS server with all the values in the column and the **State** attribute of the **Supplier** entity will be populated with values from the **State** entity.</span></span> <span data-ttu-id="50898-105">À présent, le modèle **fournisseurs** doit avoir deux entités : **fournisseur** et **État** où l’attribut **État** de l’entité **fournisseur** est un attribut basé sur un domaine qui dépend de l’entité **État** .</span><span class="sxs-lookup"><span data-stu-id="50898-105">Now, the **Suppliers** model should have two entities: **Supplier** and **State** where the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on **State** entity.</span></span>  
  
1.  <span data-ttu-id="50898-106">Basculez vers la fenêtre **Excel** avec **nettoyage et mis en correspondance Suppliers.xlsx** ouvrir.</span><span class="sxs-lookup"><span data-stu-id="50898-106">Switch to **Excel** window that has **Cleansed and Matched Suppliers.xlsx** open.</span></span>  
  
2.  <span data-ttu-id="50898-107">Cliquez sur le bouton **Actualiser** du ruban pour accéder aux dernières mises à jour de MDS.</span><span class="sxs-lookup"><span data-stu-id="50898-107">Click **Refresh** button on the ribbon to get the latest updates from MDS.</span></span> <span data-ttu-id="50898-108">Vous devez voir les deux autres enregistrements si vous avez effectué la **tâche facultative 4**.</span><span class="sxs-lookup"><span data-stu-id="50898-108">You should see the two more records if you have performed the optional **Task 4**.</span></span>  
  
3.  <span data-ttu-id="50898-109">Cliquez sur **État** du nom de colonne (cellule **I1**) dans la **ligne d’en-tête**.</span><span class="sxs-lookup"><span data-stu-id="50898-109">Click column name **State** (cell **I1**) in the **header row**.</span></span>  
  
     <span data-ttu-id="50898-110">![Excel - Bouton Propriétés d'attributs](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Bouton Propriétés d'attributs")</span><span class="sxs-lookup"><span data-stu-id="50898-110">![Excel - Attribute Properties Button](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Attribute Properties Button")</span></span>  
  
4.  <span data-ttu-id="50898-111">Cliquez sur Propriétés de l' **attribut** dans le ruban.</span><span class="sxs-lookup"><span data-stu-id="50898-111">Click **Attribute Properties** on the ribbon.</span></span>  
  
5.  <span data-ttu-id="50898-112">Dans la boîte de dialogue Propriétés de l' **attribut** , sélectionnez **liste restreinte (basée sur un domaine)** pour le **type d’attribut**.</span><span class="sxs-lookup"><span data-stu-id="50898-112">In the **Attribute Properties** dialog box, select **Constrained list (Domain-based)** for the **Attribute type**.</span></span>  
  
6.  <span data-ttu-id="50898-113">Tapez **State** pour le **nouveau nom d’entité** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50898-113">Type **State** for the **New entity name** and click **OK**.</span></span>  
  
     <span data-ttu-id="50898-114">![Excel - Boîte de dialogue Propriétés d'attributs](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Boîte de dialogue Propriétés d'attributs")</span><span class="sxs-lookup"><span data-stu-id="50898-114">![Excel - Attribute Properties Dialog Box](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Attribute Properties Dialog Box")</span></span>  
  
7.  <span data-ttu-id="50898-115">Désormais, dans Excel, vous devriez voir une **flèche vers le bas** lorsque vous cliquez sur une valeur dans la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="50898-115">Now, in Excel, you should see **down arrow** when you click any value in the **State** column.</span></span> <span data-ttu-id="50898-116">Modifiez la valeur à l'aide de la liste déroulante, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="50898-116">You can change the value by using the drop-down list if you need.</span></span>  
  
     <span data-ttu-id="50898-117">![Excel - Liste déroulante des États](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Liste déroulante des États")</span><span class="sxs-lookup"><span data-stu-id="50898-117">![Excel - Drop Down List with States](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Drop Down List with States")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="50898-118">étape suivante</span><span class="sxs-lookup"><span data-stu-id="50898-118">Next Step</span></span>  
 [<span data-ttu-id="50898-119">Tâche 6 : Tâche 6 : Vérification que l’attribut basé sur un domaine est créé à l’aide de Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="50898-119">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>](../../2014/tutorials/task-6-verify-domain-based-attribute-master-data-manager.md)  
  
  
