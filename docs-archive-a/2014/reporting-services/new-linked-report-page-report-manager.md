---
title: Page nouveau rapport lié (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fefb46e8-6901-4d50-a3f8-7c49ad72e7b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61138e51cfd9bb6e1ee124dd4aa3bc224d8aebcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612193"
---
# <a name="new-linked-report-page-report-manager"></a><span data-ttu-id="2a7fd-102">Page Nouveau rapport lié (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="2a7fd-102">New Linked Report Page (Report Manager)</span></span>
  <span data-ttu-id="2a7fd-103">La page Nouveau rapport lié vous permet de créer un rapport lié.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-103">Use the New Linked Report page to create a linked report.</span></span> <span data-ttu-id="2a7fd-104">Un rapport lié est un rapport qui possède ses propres paramètres et propriétés, mais qui est lié à la définition de rapport d'un autre rapport.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-104">A linked report is a report with settings and properties of its own, but links to the report definition of another report.</span></span> <span data-ttu-id="2a7fd-105">Les rapports liés sont utiles lorsque vous possédez un rapport de base que vous souhaitez modifier pour des groupes ou des utilisateurs spécifiques (par exemple, un rapport régional qui retourne des données différentes selon le code de région que vous spécifiez en tant que paramètre).</span><span class="sxs-lookup"><span data-stu-id="2a7fd-105">Linked reports are useful when you have a base report that you want to vary for specific groups or users; for example, a regional report that returns different data based on a regional code that you specify as a parameter.</span></span> <span data-ttu-id="2a7fd-106">Un rapport lié est généralement créé à partir d'un rapport paramétrable lorsque vous souhaitez modifier puis enregistrer des valeurs de paramètres différentes avec chaque instance du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-106">A linked report is typically created from a parameterized report when you want to vary and then save different parameter values with each report instance.</span></span> <span data-ttu-id="2a7fd-107">Toutefois, vous pouvez créer un rapport lié à partir de n'importe quel rapport auquel vous avez accès.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-107">However, you can create a linked report from any report to which you have access.</span></span>  
  
 <span data-ttu-id="2a7fd-108">Un rapport lié peut posséder son nom, sa description, son emplacement, ses propriétés de paramètres, ses propriétés d'exécution de rapport, ses propriétés d'historique de rapport, ses autorisations et ses abonnements propres.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-108">A linked report can have its own name, description, location, parameter properties, report execution properties, report history properties, permissions, and subscriptions.</span></span> <span data-ttu-id="2a7fd-109">Toutefois, un rapport lié doit utiliser les propriétés de source de données et la mise en page du rapport de base qui fournit la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-109">However, a linked report must use the data source properties and layout of the base report that provides the report definition.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="2a7fd-110">Navigation</span><span class="sxs-lookup"><span data-stu-id="2a7fd-110">Navigation</span></span>  
 <span data-ttu-id="2a7fd-111">Utilisez les procédures suivantes pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-111">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-contents-page"></a><span data-ttu-id="2a7fd-112">Pour ouvrir la page Nouveau rapport lié depuis la page Contenu</span><span class="sxs-lookup"><span data-stu-id="2a7fd-112">To open the New Linked Report page from the Contents page</span></span>  
  
1.  <span data-ttu-id="2a7fd-113">Ouvrez le Gestionnaire de rapports et recherchez un rapport pour lequel vous souhaitez créer un rapport lié.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-113">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="2a7fd-114">Pointez sur le rapport et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-114">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="2a7fd-115">Dans le menu déroulant, cliquez sur **Créer un rapport lié**.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-115">In the drop-down menu, click **Create Linked Report**.</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-general-properties-page-of-a-report"></a><span data-ttu-id="2a7fd-116">Pour ouvrir la page Nouveau rapport lié dans la page des propriétés générales d'un rapport</span><span class="sxs-lookup"><span data-stu-id="2a7fd-116">To open the New Linked Report page from the General properties page of a report</span></span>  
  
1.  <span data-ttu-id="2a7fd-117">Ouvrez le Gestionnaire de rapports et recherchez un rapport pour lequel vous souhaitez créer un rapport lié.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-117">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="2a7fd-118">Pointez sur le rapport et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="2a7fd-119">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-119">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="2a7fd-120">La page des propriétés générales pour le rapport s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-120">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="2a7fd-121">Dans la barre d'outils de l'élément, cliquez sur **Créer un rapport lié**.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-121">In the item toolbar, click **Create Linked Report**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2a7fd-122">Options</span><span class="sxs-lookup"><span data-stu-id="2a7fd-122">Options</span></span>  
 <span data-ttu-id="2a7fd-123">**Nom**</span><span class="sxs-lookup"><span data-stu-id="2a7fd-123">**Name**</span></span>  
 <span data-ttu-id="2a7fd-124">Spécifie le nom du rapport lié.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-124">Specify the name of the linked report.</span></span> <span data-ttu-id="2a7fd-125">Le nom doit contenir un caractère alphanumérique au minimum.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-125">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="2a7fd-126">Il peut également comporter des espaces et certains symboles.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-126">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="2a7fd-127">Toutefois, vous ne devez pas utiliser les caractères ; ?</span><span class="sxs-lookup"><span data-stu-id="2a7fd-127">However, you must not use the characters ; ?</span></span> <span data-ttu-id="2a7fd-128">: \@ & = +, $/\* \< > | "ou/lorsque vous spécifiez un nom.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-128">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="2a7fd-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="2a7fd-129">**Description**</span></span>  
 <span data-ttu-id="2a7fd-130">Tapez une description du contenu du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-130">Type a description of the report contents.</span></span> <span data-ttu-id="2a7fd-131">Cette description apparaît dans la page Contenu. Elle est visible par les utilisateurs qui sont autorisés à accéder au rapport.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-131">This description appears in the Contents page to users who have permission to access the report.</span></span>  
  
 <span data-ttu-id="2a7fd-132">**Lieu**</span><span class="sxs-lookup"><span data-stu-id="2a7fd-132">**Location**</span></span>  
 <span data-ttu-id="2a7fd-133">Spécifie le chemin d'accès au dossier qui contient le rapport.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-133">Specify the folder path that contains the report.</span></span> <span data-ttu-id="2a7fd-134">Par défaut, les rapports liés sont créés comme des frères du rapport de base.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-134">By default, linked reports are created as siblings to the base report.</span></span> <span data-ttu-id="2a7fd-135">Cliquez sur **Modifier l'emplacement** pour placer le rapport lié dans un autre dossier.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-135">Click **Change Location** to put the linked report in a different folder.</span></span>  
  
 <span data-ttu-id="2a7fd-136">**OK**</span><span class="sxs-lookup"><span data-stu-id="2a7fd-136">**OK**</span></span>  
 <span data-ttu-id="2a7fd-137">Cliquez sur **OK** pour enregistrer vos modifications et retourner à la page des propriétés générales du rapport de base.</span><span class="sxs-lookup"><span data-stu-id="2a7fd-137">Click **OK** to save your changes and return to the General properties page of the base report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a7fd-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a7fd-138">See Also</span></span>  
 <span data-ttu-id="2a7fd-139">[Créer un rapport lié](reports/create-a-linked-report.md) </span><span class="sxs-lookup"><span data-stu-id="2a7fd-139">[Create a Linked Report](reports/create-a-linked-report.md) </span></span>  
 <span data-ttu-id="2a7fd-140">[Page Propriétés générales, rapports &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2a7fd-140">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 [<span data-ttu-id="2a7fd-141">Aide F1 du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="2a7fd-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
