---
title: Boîte de dialogue Valider | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackagevalidate.f1
- sql12.ssis.ssms.isprojectvalidate.f1
ms.assetid: 134e14ce-4f8d-4a20-889a-918014c841d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 69e29d106dc9f4f100bf191911c5c34e0250be8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601623"
---
# <a name="validate-dialog-box"></a><span data-ttu-id="ddbb1-102">Boîte de dialogue Valider</span><span class="sxs-lookup"><span data-stu-id="ddbb1-102">Validate Dialog Box</span></span>
  <span data-ttu-id="ddbb1-103">Utilisez la boîte de dialogue **Valider** pour examiner les problèmes usuels d'un projet ou package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddbb1-103">Use the **Validate** dialog box to check for common problems in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a project or package.</span></span>  
  
 <span data-ttu-id="ddbb1-104">En cas de problème, un message s'affiche en haut de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-104">If there is a problem, a message is displayed at the top of the dialog box.</span></span> <span data-ttu-id="ddbb1-105">Sinon, le terme Prêt s'affiche en haut.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-105">Otherwise, the term Ready displays at the top.</span></span>  
  
 <span data-ttu-id="ddbb1-106">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="ddbb1-107">Ouvrir la boîte de dialogue Valider</span><span class="sxs-lookup"><span data-stu-id="ddbb1-107">Open the Validate dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="ddbb1-108">Définir les options sur la page Général</span><span class="sxs-lookup"><span data-stu-id="ddbb1-108">Set the options on the General page</span></span>](#general)  
  
##  <a name="open-the-validate-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="ddbb1-109">Ouvrir la boîte de dialogue Valider</span><span class="sxs-lookup"><span data-stu-id="ddbb1-109">Open the Validate dialog box</span></span>  
  
1.  <span data-ttu-id="ddbb1-110">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddbb1-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="ddbb1-111">Vous vous connectez à l’instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données SSISDB.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-111">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="ddbb1-112">Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .</span><span class="sxs-lookup"><span data-stu-id="ddbb1-112">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="ddbb1-113">Développez le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="ddbb1-113">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="ddbb1-114">Développez le dossier qui contient le projet ou package à valider.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-114">Expand the folder that contains the project or package you want to validate.</span></span>  
  
5.  <span data-ttu-id="ddbb1-115">Cliquez avec le bouton droit sur le projet ou le package, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-115">Right-click the package or package, and then click **Validate**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="ddbb1-116">Définir les options sur la page Général</span><span class="sxs-lookup"><span data-stu-id="ddbb1-116">Set the options on the General page</span></span>  
 <span data-ttu-id="ddbb1-117">**Environment**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-117">**Environment**</span></span>  
 <span data-ttu-id="ddbb1-118">Sélectionnez l'environnement à utiliser pour valider le projet ou le package.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-118">Select the environment that you want to use to validate the project or package.</span></span>  
  
 <span data-ttu-id="ddbb1-119">**Runtime 32 bits**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-119">**32-bit runtime**</span></span>  
 <span data-ttu-id="ddbb1-120">Sélectionnez cette option afin d'utiliser un runtime 32 bits pour exécuter un package.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-120">Select to use a 32-bit runtime to execute a package.</span></span>  
  
 <span data-ttu-id="ddbb1-121">L'onglet **Paramètres** indique les valeurs de paramètres que vous utilisez pour valider le projet ou le package.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-121">The **Parameters** tab lists the parameter values that you use to validate the project or package.</span></span> <span data-ttu-id="ddbb1-122">Voici les options de l'onglet Paramètres.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-122">The following are the options on the Parameters tab.</span></span>  
  
 <span data-ttu-id="ddbb1-123">**Conteneur**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-123">**Container**</span></span>  
 <span data-ttu-id="ddbb1-124">Indique l'objet qui contient le paramètre.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-124">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="ddbb1-125">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-125">**Parameter**</span></span>  
 <span data-ttu-id="ddbb1-126">Indique le nom des paramètres.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-126">Lists the name of the parameters</span></span>  
  
 <span data-ttu-id="ddbb1-127">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-127">**Value**</span></span>  
 <span data-ttu-id="ddbb1-128">Indique la valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-128">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="ddbb1-129">L'onglet **Gestionnaires de connexions** indique les valeurs de propriétés du gestionnaire de connexions que vous utilisez pour valider le projet ou le package.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-129">The **Connection Managers** tab lists the connection manager property values that you use to validate the project or package.</span></span>  
  
 <span data-ttu-id="ddbb1-130">Voici les options de l'onglet **Gestionnaires de connexions** .</span><span class="sxs-lookup"><span data-stu-id="ddbb1-130">The following are the options on the **Connection Managers** tab.</span></span>  
  
 <span data-ttu-id="ddbb1-131">**Conteneur**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-131">**Container**</span></span>  
 <span data-ttu-id="ddbb1-132">Indique l'objet qui contient le gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-132">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="ddbb1-133">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-133">**Name**</span></span>  
 <span data-ttu-id="ddbb1-134">Indique le nom du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-134">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="ddbb1-135">**Nom de la propriété**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-135">**Property name**</span></span>  
 <span data-ttu-id="ddbb1-136">Indique le nom de la propriété du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-136">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="ddbb1-137">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="ddbb1-137">**Value**</span></span>  
 <span data-ttu-id="ddbb1-138">Indique la valeur affectée à la propriété du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="ddbb1-138">Lists the value assigned to the connection manager property.</span></span>  
  
  
