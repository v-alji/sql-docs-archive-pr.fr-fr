---
title: Boîte de dialogue Configurer | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.SSIS.SSMS.ISPROJECTPROP.PARAMETERS.F1
- SQL12.SSIS.SSMS.ISPROJECTPROP.REFERENCES.F1
- sql12.dts.designer.configure.f1
ms.assetid: 10183c8d-b1be-420f-972a-96ea97d4f4d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857baf3421f2744144e10b0df0b770538f533192
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611244"
---
# <a name="configure-dialog-box"></a><span data-ttu-id="b1e42-102">Boîte de dialogue Configurer</span><span class="sxs-lookup"><span data-stu-id="b1e42-102">Configure Dialog Box</span></span>
  <span data-ttu-id="b1e42-103">Utilisez la boîte de dialogue **Configurer** pour configurer les paramètres, les gestionnaires de connexions, ainsi que les références aux environnements, pour les packages et les projets.</span><span class="sxs-lookup"><span data-stu-id="b1e42-103">Use the **Configure** dialog box to configure parameters, connection managers, and references to environments, for packages and projects.</span></span>  
  
 <span data-ttu-id="b1e42-104">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="b1e42-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="b1e42-105">Ouvrir la boîte de dialogue Configurer</span><span class="sxs-lookup"><span data-stu-id="b1e42-105">Open the Configure Dialog Box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="b1e42-106">Définir les options de la page Paramètres</span><span class="sxs-lookup"><span data-stu-id="b1e42-106">Set the options on the Parameters page</span></span>](#parameter)  
  
-   [<span data-ttu-id="b1e42-107">Définir les options de la page Références</span><span class="sxs-lookup"><span data-stu-id="b1e42-107">Set the options on the References page</span></span>](#references)  
  
##  <a name="open-the-configure-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="b1e42-108">Ouvrir la boîte de dialogue Configurer</span><span class="sxs-lookup"><span data-stu-id="b1e42-108">Open the Configure Dialog Box</span></span>  
  
1.  <span data-ttu-id="b1e42-109">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b1e42-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="b1e42-110">Vous vous connectez à l’instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données SSISDB.</span><span class="sxs-lookup"><span data-stu-id="b1e42-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="b1e42-111">Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .</span><span class="sxs-lookup"><span data-stu-id="b1e42-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="b1e42-112">Développez le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="b1e42-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="b1e42-113">Développez le dossier qui contient le package ou le projet à configurer.</span><span class="sxs-lookup"><span data-stu-id="b1e42-113">Expand the folder that contains the package or project that you want to configure.</span></span>  
  
5.  <span data-ttu-id="b1e42-114">Cliquez avec le bouton droit sur le package ou le projet, puis cliquez sur **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="b1e42-114">Right-click the package or project, and then click **Configure**.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-page"></a><a name="parameter"></a> <span data-ttu-id="b1e42-115">Définir les options de la page Paramètres</span><span class="sxs-lookup"><span data-stu-id="b1e42-115">Set the options on the Parameters page</span></span>  
 <span data-ttu-id="b1e42-116">Utilisez la page **Paramètres** pour afficher les noms et valeurs des paramètres, ainsi que pour modifier ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="b1e42-116">Use the **Parameters** page to view parameter names and values, and to modify the values.</span></span>  
  
 <span data-ttu-id="b1e42-117">Sélectionnez l’étendue des paramètres affichés sous les onglets **Paramètres** et **Gestionnaires de connexions** , dans la liste déroulante **Étendue** .</span><span class="sxs-lookup"><span data-stu-id="b1e42-117">Select the scope of the parameters displayed in the **Parameters** and **Connection Managers** tabs, in the **Scope** drop-down list.</span></span>  
  
 <span data-ttu-id="b1e42-118">Vous trouverez ci-dessous la liste des options de l'onglet **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="b1e42-118">The following is a list of the options in the **Parameters** tab.</span></span>  
  
 <span data-ttu-id="b1e42-119">**Conteneur**</span><span class="sxs-lookup"><span data-stu-id="b1e42-119">**Container**</span></span>  
 <span data-ttu-id="b1e42-120">Indique l'objet qui contient le paramètre.</span><span class="sxs-lookup"><span data-stu-id="b1e42-120">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="b1e42-121">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b1e42-121">**Name**</span></span>  
 <span data-ttu-id="b1e42-122">Indique le nom du paramètre.</span><span class="sxs-lookup"><span data-stu-id="b1e42-122">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="b1e42-123">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="b1e42-123">**Value**</span></span>  
 <span data-ttu-id="b1e42-124">Indique la valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="b1e42-124">Lists the parameter value.</span></span> <span data-ttu-id="b1e42-125">Cliquez sur le bouton de sélection pour modifier la valeur dans la boîte de dialogue **Définir la valeur du paramètre** .</span><span class="sxs-lookup"><span data-stu-id="b1e42-125">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span>  
  
 <span data-ttu-id="b1e42-126">Vous trouverez ci-dessous la liste des options de l'onglet **Gestionnaires de connexions** . Utilisez cet onglet pour modifier les valeurs des propriétés du Gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="b1e42-126">The following is a list of the options in the **Connection Managers** tab. You use this tab to change values for connection manager properties.</span></span> <span data-ttu-id="b1e42-127">Les paramètres sont automatiquement générés sur le serveur SSIS pour les propriétés.</span><span class="sxs-lookup"><span data-stu-id="b1e42-127">Parameters are automatically generated on the SSIS server for the properties.</span></span>  
  
 <span data-ttu-id="b1e42-128">**Conteneur**</span><span class="sxs-lookup"><span data-stu-id="b1e42-128">**Container**</span></span>  
 <span data-ttu-id="b1e42-129">Indique l'objet qui contient le gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="b1e42-129">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="b1e42-130">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b1e42-130">**Name**</span></span>  
 <span data-ttu-id="b1e42-131">Indique le nom du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="b1e42-131">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="b1e42-132">**Nom de la propriété**</span><span class="sxs-lookup"><span data-stu-id="b1e42-132">**Property name**</span></span>  
 <span data-ttu-id="b1e42-133">Indique le nom de la propriété du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="b1e42-133">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="b1e42-134">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="b1e42-134">**Value**</span></span>  
 <span data-ttu-id="b1e42-135">Indique la valeur affectée à la propriété du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="b1e42-135">Lists the value assigned to the connection manager property.</span></span> <span data-ttu-id="b1e42-136">Cliquez sur le bouton de sélection pour modifier la valeur dans la boîte de dialogue **Définir la valeur du paramètre** .</span><span class="sxs-lookup"><span data-stu-id="b1e42-136">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span> <span data-ttu-id="b1e42-137">Vous pouvez entrer une valeur littérale, mapper une variable d'environnement qui contient la valeur à utiliser, ou utiliser la valeur par défaut du package.</span><span class="sxs-lookup"><span data-stu-id="b1e42-137">You can enter a literal value, map an environment variable that contains the value you want to use, or use the default value from the package.</span></span>  
  
##  <a name="set-the-options-on-the-references-page"></a><a name="references"></a> <span data-ttu-id="b1e42-138">Définir les options de la page Références</span><span class="sxs-lookup"><span data-stu-id="b1e42-138">Set the options on the References page</span></span>  
 <span data-ttu-id="b1e42-139">Utilisez la page **Références** pour ajouter et supprimer des références aux environnements, ainsi que pour accéder aux propriétés des environnements.</span><span class="sxs-lookup"><span data-stu-id="b1e42-139">Use the **References** page to add and remove references to environments, and to access environment properties.</span></span>  
  
 <span data-ttu-id="b1e42-140">Un environnement spécifie les valeurs d’exécution des packages contenus dans les projets que vous avez déployés sur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1e42-140">An environment specifies runtime values for packages contained in the projects you've deployed to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="b1e42-141">**Environment**</span><span class="sxs-lookup"><span data-stu-id="b1e42-141">**Environment**</span></span>  
 <span data-ttu-id="b1e42-142">Indique l'environnement.</span><span class="sxs-lookup"><span data-stu-id="b1e42-142">Lists the environment.</span></span>  
  
 <span data-ttu-id="b1e42-143">**Dossier d'environnement**</span><span class="sxs-lookup"><span data-stu-id="b1e42-143">**Environment Folder**</span></span>  
 <span data-ttu-id="b1e42-144">Indique le dossier qui contient l'environnement.</span><span class="sxs-lookup"><span data-stu-id="b1e42-144">Lists the folder that contains the environment.</span></span>  
  
 <span data-ttu-id="b1e42-145">**Ouvrir**</span><span class="sxs-lookup"><span data-stu-id="b1e42-145">**Open**</span></span>  
 <span data-ttu-id="b1e42-146">Cliquez pour ouvrir la boîte de dialogue **Propriétés d’environnement** .</span><span class="sxs-lookup"><span data-stu-id="b1e42-146">Click to open the **Environment Properties** dialog box.</span></span>  
  
 <span data-ttu-id="b1e42-147">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="b1e42-147">**Add**</span></span>  
 <span data-ttu-id="b1e42-148">Cliquez pour ajouter une référence à un environnement.</span><span class="sxs-lookup"><span data-stu-id="b1e42-148">Click to add a reference to an environment.</span></span> <span data-ttu-id="b1e42-149">Dans la boîte de dialogue **Parcourir les environnements** , cliquez sur un environnement, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1e42-149">In the **Browse Environments** dialog box click an environment and then click **OK**.</span></span>  
  
 <span data-ttu-id="b1e42-150">Vous pouvez sélectionner un environnement contenu dans n'importe quel dossier de projet sous le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="b1e42-150">You can select an environment contained in any project folder under the **SSISDB** node.</span></span>  
  
 <span data-ttu-id="b1e42-151">**Remove**</span><span class="sxs-lookup"><span data-stu-id="b1e42-151">**Remove**</span></span>  
 <span data-ttu-id="b1e42-152">Cliquez sur un environnement répertorié dans la zone **Références** , puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b1e42-152">Click an environment listed in the **References** area, and then click **Remove**.</span></span>  
  
  
