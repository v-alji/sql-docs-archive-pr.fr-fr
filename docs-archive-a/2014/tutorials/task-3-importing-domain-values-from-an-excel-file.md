---
title: 'Tâche 3 : importation des valeurs de domaine à partir d’un fichier Excel | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 242e8309-1195-495b-9cd5-aa127748c185
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 707a3925bb6d0014e2a1248f904123b076024e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601840"
---
# <a name="task-3-importing-domain-values-from-an-excel-file"></a><span data-ttu-id="4acaa-102">Tâche 3 : Importer des valeurs de domaine d’un fichier Excel</span><span class="sxs-lookup"><span data-stu-id="4acaa-102">Task 3: Importing Domain Values from an Excel File</span></span>

  <span data-ttu-id="4acaa-103">Dans cette tâche, vous allez importer les valeurs du domaine **État** à partir d'une feuille de calcul d'un fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="4acaa-103">In this task, you import values for the **State** domain from a worksheet of an Excel file.</span></span>

1.  <span data-ttu-id="4acaa-104">Cliquez sur le domaine **État** dans la **liste des domaines**.</span><span class="sxs-lookup"><span data-stu-id="4acaa-104">Click **State** domain in the **Domain list**.</span></span>

2.  <span data-ttu-id="4acaa-105">Assurez-vous que l'onglet **Valeurs du domaine** est actif dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="4acaa-105">Ensure that the **Domain Values** tab is active in the right pane.</span></span>

3.  <span data-ttu-id="4acaa-106">Dans le volet droit, dans la barre d'outils, cliquez sur la **flèche vers le bas** en regard du bouton **Importer des valeurs** , puis cliquez sur **Importer des valeurs valides d'Excel**.</span><span class="sxs-lookup"><span data-stu-id="4acaa-106">In the right pane, from the toolbar, click **down arrow** next to the **Import Values** button, and click **Import Valid Values from Excel**.</span></span>

     <span data-ttu-id="4acaa-107">![Importer les valeurs valides du menu d'Excel](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Importer les valeurs valides du menu d'Excel")</span><span class="sxs-lookup"><span data-stu-id="4acaa-107">![Import Valid Values from Excel Menu](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Import Valid Values from Excel Menu")</span></span>

4.  <span data-ttu-id="4acaa-108">Cliquez sur **Parcourir**, sélectionnez **Suppliers.xls**, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="4acaa-108">Click **Browse**, select **Suppliers.xls**, and click **Open**.</span></span>

5.  <span data-ttu-id="4acaa-109">Sélectionnez **StatesToImport$** pour **Feuille de calcul**.</span><span class="sxs-lookup"><span data-stu-id="4acaa-109">Select **StatesToImport$** for the **Worksheet**.</span></span>

     <span data-ttu-id="4acaa-110">![Boîte de dialogue Importer les valeurs du domaine](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Boîte de dialogue Importer les valeurs du domaine")</span><span class="sxs-lookup"><span data-stu-id="4acaa-110">![Import Domain Values Dialog Box](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Import Domain Values Dialog Box")</span></span>

6.  <span data-ttu-id="4acaa-111">Cliquez sur **OK** pour fermer la boîte de dialogue **Importer les valeurs du domaine** .</span><span class="sxs-lookup"><span data-stu-id="4acaa-111">Click **OK** to close the **Import Domain Values** dialog box.</span></span> <span data-ttu-id="4acaa-112">Vous devez voir les noms des États que vous avez importés dans la liste.</span><span class="sxs-lookup"><span data-stu-id="4acaa-112">You should see all the names of states you imported in the list.</span></span> <span data-ttu-id="4acaa-113">Notez que l'option **Afficher seulement les nouvelles valeurs** est sélectionnée automatiquement après l'importation.</span><span class="sxs-lookup"><span data-stu-id="4acaa-113">Notice that **Show Only New** option is automatically selected after importing.</span></span> <span data-ttu-id="4acaa-114">Lorsque vous importez des valeurs et que vous ne voyez pas les anciennes valeurs dans la liste, cela est dû au fait que cette option est activée automatiquement après l’importation.</span><span class="sxs-lookup"><span data-stu-id="4acaa-114">When you import values and you don't see the old values in the list, it is because this option is automatically enabled after importing.</span></span> <span data-ttu-id="4acaa-115">Pour afficher toutes les valeurs, désactivez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="4acaa-115">To see all the values, clear the check box.</span></span> <span data-ttu-id="4acaa-116">Si vous réimportez le même jeu de valeurs, aucune valeur n'est importée car elles existent déjà dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="4acaa-116">If you import the same set of values again, none of the values are imported as they already exist in the domain.</span></span>

     <span data-ttu-id="4acaa-117">![Afficher uniquement une nouvelle case à cocher dans les valeurs de domaine](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Afficher uniquement une nouvelle case à cocher dans les valeurs de domaine")</span><span class="sxs-lookup"><span data-stu-id="4acaa-117">![Show Only New Checkbox on Domain Values](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Show Only New Checkbox on Domain Values")</span></span>

## <a name="next-step"></a><span data-ttu-id="4acaa-118">étape suivante</span><span class="sxs-lookup"><span data-stu-id="4acaa-118">Next Step</span></span>
 [<span data-ttu-id="4acaa-119">Tâche 4 : Définition de règles de domaine</span><span class="sxs-lookup"><span data-stu-id="4acaa-119">Task 4: Setting Domain Rules</span></span>](../../2014/tutorials/task-4-setting-domain-rules.md)


