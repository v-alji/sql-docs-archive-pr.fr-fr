---
title: Boîte de dialogue Définir la valeur du paramètre | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ce9c2201-4e9a-4495-948f-b68deeaa7955
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 637267603c66921a566ca0d2a3f49f6142cfd203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705355"
---
# <a name="set-parameter-value-dialog-box"></a><span data-ttu-id="917c6-102">Boîte de dialogue Définir la valeur du paramètre</span><span class="sxs-lookup"><span data-stu-id="917c6-102">Set Parameter Value Dialog Box</span></span>
  <span data-ttu-id="917c6-103">Utilisez la boîte de dialogue **Définir la valeur du paramètre** pour définir les valeurs des paramètres et les propriétés des gestionnaires de connexions, pour les projets et packages.</span><span class="sxs-lookup"><span data-stu-id="917c6-103">Use the **Set Parameter Value** dialog box to set values for parameters and connection manager properties, for projects and packages.</span></span>  
  
 <span data-ttu-id="917c6-104">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="917c6-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="917c6-105">Ouvrir la boîte de dialogue Définir la valeur du paramètre</span><span class="sxs-lookup"><span data-stu-id="917c6-105">Open the Set Parameter Value dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="917c6-106">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="917c6-106">Configure the options</span></span>](#option)  
  
##  <a name="open-the-set-parameter-value-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="917c6-107">Ouvrir la boîte de dialogue Définir la valeur du paramètre</span><span class="sxs-lookup"><span data-stu-id="917c6-107">Open the Set Parameter Value dialog box</span></span>  
  
1.  <span data-ttu-id="917c6-108">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="917c6-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="917c6-109">Vous vous connectez à l’instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données SSISDB.</span><span class="sxs-lookup"><span data-stu-id="917c6-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="917c6-110">Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .</span><span class="sxs-lookup"><span data-stu-id="917c6-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="917c6-111">Développez le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="917c6-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="917c6-112">Cliquez avec le bouton droit sur un package ou un projet, cliquez sur **Configurer**, puis cliquez sur le bouton de sélection sous l’onglet **Paramètres** ou l’onglet **Gestionnaires de connexions** .</span><span class="sxs-lookup"><span data-stu-id="917c6-112">Right-click a package or project, click **Configure**, and then click the ellipsis button in the **Parameters** tab or in the **Connection Managers** tab.</span></span>  
  
##  <a name="configure-the-options"></a><a name="option"></a> <span data-ttu-id="917c6-113">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="917c6-113">Configure the options</span></span>  
 <span data-ttu-id="917c6-114">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="917c6-114">**Parameter**</span></span>  
 <span data-ttu-id="917c6-115">Indique le nom du paramètre.</span><span class="sxs-lookup"><span data-stu-id="917c6-115">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="917c6-116">**Type**</span><span class="sxs-lookup"><span data-stu-id="917c6-116">**Type**</span></span>  
 <span data-ttu-id="917c6-117">Indique le type de données de la valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="917c6-117">Lists the data type of the parameter value.</span></span>  
  
 <span data-ttu-id="917c6-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="917c6-118">**Description**</span></span>  
 <span data-ttu-id="917c6-119">Affiche une description facultative du paramètre.</span><span class="sxs-lookup"><span data-stu-id="917c6-119">Shows an optional description for the parameter.</span></span>  
  
 <span data-ttu-id="917c6-120">**Modifier la valeur**</span><span class="sxs-lookup"><span data-stu-id="917c6-120">**Edit value**</span></span>  
 <span data-ttu-id="917c6-121">Sélectionnez cette option pour modifier la valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="917c6-121">Select this option to edit the parameter value.</span></span>  
  
 <span data-ttu-id="917c6-122">**Utiliser la valeur par défaut du package**</span><span class="sxs-lookup"><span data-stu-id="917c6-122">**Use default value from package**</span></span>  
 <span data-ttu-id="917c6-123">Sélectionnez cette option afin d'utiliser le paramètre par défaut stocké dans le package.</span><span class="sxs-lookup"><span data-stu-id="917c6-123">Select this option to use the default parameter value stored in the package.</span></span>  
  
 <span data-ttu-id="917c6-124">**Utiliser la variable d'environnement**</span><span class="sxs-lookup"><span data-stu-id="917c6-124">**Use environment variable**</span></span>  
 <span data-ttu-id="917c6-125">Sélectionnez cette option pour utiliser une valeur de variable stockée dans l'environnement, qui est référencé par le projet ou le package.</span><span class="sxs-lookup"><span data-stu-id="917c6-125">Select this option to use a variable value stored in the environment, which is referenced by the project or package.</span></span> <span data-ttu-id="917c6-126">Pour ajouter une référence d'environnement à un projet ou package, utilisez la boîte de dialogue **Configurer** .</span><span class="sxs-lookup"><span data-stu-id="917c6-126">To add an environment reference to a project or package, use the **Configure** dialog box.</span></span> <span data-ttu-id="917c6-127">Pour plus d'informations, consultez [Configure Dialog Box](configure-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="917c6-127">For more information, see [Configure Dialog Box](configure-dialog-box.md).</span></span>  
  
  
