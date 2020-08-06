---
title: 'Tâche 6 : définition des synonymes | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b7d35ee9-d1c9-41d9-bbc5-0ca7db93e54d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bde0c0ec7f230ba2325aa01328b191fd8fd67fa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600397"
---
# <a name="task-6-setting-synonyms"></a><span data-ttu-id="b2947-102">Tâche 6 : Définition des synonymes</span><span class="sxs-lookup"><span data-stu-id="b2947-102">Task 6: Setting Synonyms</span></span>
  <span data-ttu-id="b2947-103">Dans cette tâche, vous devez définir deux valeurs de domaine, **USA** et **États-Unis**, du domaine **Pays** comme synonymes, avec **États-Unis** comme valeur menante.</span><span class="sxs-lookup"><span data-stu-id="b2947-103">In this task, you set two domain values, **USA** and **United States**, of the **Country** domain as synonyms with **United States** as the leading value.</span></span> <span data-ttu-id="b2947-104">Dans la mesure où l'option **Utiliser des valeurs menantes** a été sélectionnée lors de la création du domaine **Pays** , toutes les valeurs **USA** pour le domaine **Pays** seront remplacées par **États-Unis** (car États-Unis est la valeur menante).</span><span class="sxs-lookup"><span data-stu-id="b2947-104">Since the **Use Leading Values** option was selected when creating the **Country** domain, any **USA** values for the **Country** domain will be output as **United States** (as United States is the leading value).</span></span> <span data-ttu-id="b2947-105">Consultez [Modifier les valeurs de domaine](https://msdn.microsoft.com/library/hh510408.aspx) pour plus de détails.</span><span class="sxs-lookup"><span data-stu-id="b2947-105">See [Change Domain Values](https://msdn.microsoft.com/library/hh510408.aspx) for more details.</span></span>

1.  <span data-ttu-id="b2947-106">Sélectionnez le domaine **Pays** dans la liste des domaines.</span><span class="sxs-lookup"><span data-stu-id="b2947-106">Select **Country** from the list of domains.</span></span>

2.  <span data-ttu-id="b2947-107">Cliquez sur l'onglet **Valeurs du domaine** .</span><span class="sxs-lookup"><span data-stu-id="b2947-107">Switch to the **Domain Values** tab.</span></span>

3.  <span data-ttu-id="b2947-108">Cliquez sur le bouton **Ajouter une valeur de domaine** de la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="b2947-108">Click **Add new domain value** button on the toolbar.</span></span>

4.  <span data-ttu-id="b2947-109">Tapez **USA** pour la valeur et appuyez sur **ENTRÉE**.</span><span class="sxs-lookup"><span data-stu-id="b2947-109">Type **USA** for the value and press **ENTER**.</span></span>

5.  <span data-ttu-id="b2947-110">Sélectionnez à la fois **États-Unis** et **USA** à l'aide de la touche CTRL ou de la touche MAJ, cliquez avec le bouton droit sur les éléments sélectionnés, puis cliquez sur **Définir en tant que synonyme**.</span><span class="sxs-lookup"><span data-stu-id="b2947-110">Multiselect **United States** and **USA** using CTRL or SHIFT keys, right-click the selected items, and then click **Set as Synonyms**.</span></span> <span data-ttu-id="b2947-111">DQS regroupe ces valeurs et désigne l'une des valeurs comme valeur menante par laquelle les autres seront remplacées.</span><span class="sxs-lookup"><span data-stu-id="b2947-111">DQS groups these values and designate one of the values as the leading value that the other values are replaced with.</span></span>

     <span data-ttu-id="b2947-112">![Menu Définir en tant que synonyme](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Menu Définir en tant que synonyme")</span><span class="sxs-lookup"><span data-stu-id="b2947-112">![Set as Synonyms Menu](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Set as Synonyms Menu")</span></span>

6.  <span data-ttu-id="b2947-113">Notez que **États-Unis** est défini comme valeur menante.</span><span class="sxs-lookup"><span data-stu-id="b2947-113">Notice that **United States** is set as the leading value.</span></span> <span data-ttu-id="b2947-114">Si vous souhaitez que USA soit la valeur menante, cliquez avec le bouton droit sur USA et sélectionnez l'option **Définir en tant que valeur menante** .</span><span class="sxs-lookup"><span data-stu-id="b2947-114">If you want USA to be the leading value, you can right-click on USA and select **Set as Leading** option.</span></span> <span data-ttu-id="b2947-115">Pour ce didacticiel, nous utiliserons **États-Unis** comme valeur menante.</span><span class="sxs-lookup"><span data-stu-id="b2947-115">For this tutorial, we use **United States** as the leading value.</span></span>

     <span data-ttu-id="b2947-116">![United States et USA comme synonymes](../../2014/tutorials/media/et-settingsynonyms-02.jpg "United States et USA comme synonymes")</span><span class="sxs-lookup"><span data-stu-id="b2947-116">![United States and USA as Synonyms](../../2014/tutorials/media/et-settingsynonyms-02.jpg "United States and USA as Synonyms")</span></span>

## <a name="next-step"></a><span data-ttu-id="b2947-117">étape suivante</span><span class="sxs-lookup"><span data-stu-id="b2947-117">Next Step</span></span>
 [<span data-ttu-id="b2947-118">Tâche 7 : Création d’un domaine composite</span><span class="sxs-lookup"><span data-stu-id="b2947-118">Task 7: Creating a Composite Domain</span></span>](../../2014/tutorials/task-7-creating-a-composite-domain.md)


