---
title: Installer Analysis Services en mode tabulaire | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: cd6ac80d-b735-4e3e-a024-489f1409ad33
author: minewiskan
ms.author: owend
ms.openlocfilehash: a677fd7770f646067cafb8fedf6d3705ccf2de3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697284"
---
# <a name="install-analysis-services-in-tabular-mode"></a><span data-ttu-id="9cdb9-102">Installer Analysis Services en mode tabulaire</span><span class="sxs-lookup"><span data-stu-id="9cdb9-102">Install Analysis Services in Tabular Mode</span></span>
  <span data-ttu-id="9cdb9-103">Si vous installez Analysis Services afin d'utiliser les nouvelles fonctionnalités tabulaires de modélisation, vous devez installer Analysis Services dans un mode serveur qui prend en charge ce type de modèle.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-103">If you are installing Analysis Services to use the new tabular modeling features, you must install Analysis Services in a server mode that supports that type of model.</span></span> <span data-ttu-id="9cdb9-104">Le mode serveur est un mode tabulaire configuré pendant l'installation.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-104">The server mode is Tabular, and it is configured during installation.</span></span>  
  
 <span data-ttu-id="9cdb9-105">Après avoir installé le serveur dans ce mode, vous pouvez l'utiliser pour héberger des solutions que vous créez dans le générateur de modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-105">After you install the server in this mode, you can use it host solutions that you build in tabular model designer.</span></span> <span data-ttu-id="9cdb9-106">Un serveur en mode tabulaire est indispensable si vous souhaitez accéder aux données du modèle tabulaire par le réseau.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-106">A tabular mode server is required if you want tabular model data access over the network.</span></span>  
  
 <span data-ttu-id="9cdb9-107">Vous pouvez spécifier le mode Tabulaire dans l'Assistant Installation ou dans une installation par ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-107">You can specify Tabular mode in the Installation Wizard or in a command line setup.</span></span> <span data-ttu-id="9cdb9-108">Les sections suivantes décrivent chaque méthode.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-108">The following sections describe each approach.</span></span>  
  
## <a name="installation-wizard"></a><span data-ttu-id="9cdb9-109">Assistant Installation</span><span class="sxs-lookup"><span data-stu-id="9cdb9-109">Installation Wizard</span></span>  
 <span data-ttu-id="9cdb9-110">La liste suivante montre les pages de l'assistant Installation de SQL Server utilisées pour installer Analysis Services en mode tabulaire :</span><span class="sxs-lookup"><span data-stu-id="9cdb9-110">The following list shows you which pages in the SQL Server Installation wizard are used to install Analysis Services in Tabular mode:</span></span>  
  
1.  <span data-ttu-id="9cdb9-111">Sélectionnez **Analysis Services** dans l'Arborescence de fonctionnalités dans l'Installation.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-111">Select **Analysis Services** from the Feature Tree in Setup.</span></span>  
  
     <span data-ttu-id="9cdb9-112">![Arborescence de la fonctionnalité Programme d'installation d'Analysis Services](../../../sql-server/install/media/ssas-setupas.gif "Arborescence de la fonctionnalité Programme d'installation d'Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="9cdb9-112">![Setup feature tree showing Analsyis Services](../../../sql-server/install/media/ssas-setupas.gif "Setup feature tree showing Analsyis Services")</span></span>  
  
2.  <span data-ttu-id="9cdb9-113">Dans la page Configuration d'Analysis Services, veillez à sélectionner **Mode Tabulaire**.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-113">On the Analysis Services Configuration page, be sure to select **Tabular Mode**.</span></span>  
  
     <span data-ttu-id="9cdb9-114">![Page installation avec les options de configuration d'Analysis Services](../../../sql-server/install/media/ssas-setupasconfig.gif "Page installation avec les options de configuration d'Analysis Services")</span><span class="sxs-lookup"><span data-stu-id="9cdb9-114">![Setup page with Analysis Services config options](../../../sql-server/install/media/ssas-setupasconfig.gif "Setup page with Analysis Services config options")</span></span>  
  
 <span data-ttu-id="9cdb9-115">Le mode tabulaire utilise le moteur d'analyse en mémoire xVelocity (VertiPaq), qui est le stockage par défaut pour les modèles tabulaires que vous déployez dans Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-115">Tabular mode uses the xVelocity in-memory analytics engine (VertiPaq), which is the default storage for tabular models that you deploy to Analysis Services.</span></span> <span data-ttu-id="9cdb9-116">Après le déploiement des solutions de modèle tabulaire sur le serveur, vous pouvez configurer les solutions tabulaires de manière sélective pour qu'elles utilisent le stockage sur disque de DirectQuery comme alternative au stockage gourmand en mémoire.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-116">After you deploy tabular model solutions to the server, you can selectively configure tabular solutions to use DirectQuery disk storage as an alternative to memory-bound storage.</span></span>  
  
## <a name="command-line-setup"></a><span data-ttu-id="9cdb9-117">Installation à partir de ligne de commande</span><span class="sxs-lookup"><span data-stu-id="9cdb9-117">Command Line Setup</span></span>  
 <span data-ttu-id="9cdb9-118">L'installation de SQL Server inclut un nouveau paramètre (`ASSERVERMODE`) qui spécifie le mode serveur.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-118">SQL Server Setup includes a new parameter (`ASSERVERMODE`) that specifies the server mode.</span></span> <span data-ttu-id="9cdb9-119">L'exemple suivant illustre une installation par ligne de commande qui installe Analysis Services en mode serveur tabulaire.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-119">The following example illustrates a command line setup that installs Analysis Services in Tabular server mode.</span></span>  
  
```  
  
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /FEATURES=AS /ASSERVERMODE=TABULAR /INSTANCENAME=ASTabular /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="9cdb9-120">`INSTANCENAME` doit contenir moins de 17 caractères.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-120">`INSTANCENAME` must be less than 17 characters.</span></span>  
  
 <span data-ttu-id="9cdb9-121">Toutes les valeurs de compte de l'espace réservé doivent être remplacées par des comptes valides et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-121">All placeholder account values must be replaced with valid accounts and password.</span></span>  
  
 <span data-ttu-id="9cdb9-122">Des outils, tels que SQL Server Management Studio ou [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] , ne sont pas installés à l'aide de l'exemple de syntaxe de ligne de commande fourni.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-122">Tools such as SQL Server Management Studio or [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] are not installed using the example command line syntax that is provided.</span></span> <span data-ttu-id="9cdb9-123">Pour plus d’informations sur l’ajout de fonctionnalités, voir [installer SQL Server 2014 à partir de l’invite de commandes](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="9cdb9-123">For more information about adding features, see [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
 <span data-ttu-id="9cdb9-124">`ASSERVERMODE` respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-124">`ASSERVERMODE` is case-sensitive.</span></span>  <span data-ttu-id="9cdb9-125">Toutes les valeurs doivent être exprimées en majuscules.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-125">All values must be expressed in upper case.</span></span> <span data-ttu-id="9cdb9-126">Le tableau suivant décrit les valeurs valides pour `ASSERVERMODE`.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-126">The following table describes the valid values for `ASSERVERMODE`.</span></span>  
  
|<span data-ttu-id="9cdb9-127">Valeur</span><span class="sxs-lookup"><span data-stu-id="9cdb9-127">Value</span></span>|<span data-ttu-id="9cdb9-128">Description</span><span class="sxs-lookup"><span data-stu-id="9cdb9-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9cdb9-129">MULTIDIMENSIONAL</span><span class="sxs-lookup"><span data-stu-id="9cdb9-129">MULTIDIMENSIONAL</span></span>|<span data-ttu-id="9cdb9-130">Valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-130">This is the default value.</span></span> <span data-ttu-id="9cdb9-131">Si vous ne définissez pas `ASSERVERMODE`, le serveur est installé en mode serveur multidimensionnel.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-131">If you do not set `ASSERVERMODE`, the server is installed in Multidimensional server mode.</span></span>|  
|<span data-ttu-id="9cdb9-132">POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="9cdb9-132">POWERPIVOT</span></span>|<span data-ttu-id="9cdb9-133">Cette valeur est facultative.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-133">This value is optional.</span></span> <span data-ttu-id="9cdb9-134">En pratique, si vous définissez le paramètre `ROLE`, le mode serveur est automatiquement défini sur 1, ce qui rend `ASSERVERMODE` facultatif pour une installation de PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-134">In practice, if you set the `ROLE` parameter, the server mode is automatically set to 1, making `ASSERVERMODE` optional for a PowerPivot for SharePoint installation.</span></span> <span data-ttu-id="9cdb9-135">Pour plus d'informations, consultez [Install PowerPivot from the Command Prompt](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="9cdb9-135">For more information, see [Install PowerPivot from the Command Prompt](../../../sql-server/install/install-powerpivot-from-the-command-prompt.md).</span></span>|  
|<span data-ttu-id="9cdb9-136">TABULAR</span><span class="sxs-lookup"><span data-stu-id="9cdb9-136">TABULAR</span></span>|<span data-ttu-id="9cdb9-137">Cette valeur est obligatoire si vous installez Analysis Services en mode tabulaire à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="9cdb9-137">This value is required if you are installing Analysis Services in Tabular mode using command line setup.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cdb9-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9cdb9-138">See Also</span></span>  
 <span data-ttu-id="9cdb9-139">[Déterminer le mode serveur d’une instance de Analysis Services](../determine-the-server-mode-of-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="9cdb9-139">[Determine the Server Mode of an Analysis Services Instance](../determine-the-server-mode-of-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="9cdb9-140">[Configurer l’accès en mémoire ou DirectQuery pour une base de données model tabulaire](../../tabular-models/enable-directquery-mode-in-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="9cdb9-140">[Configure In-Memory or DirectQuery Access for a Tabular Model Database](../../tabular-models/enable-directquery-mode-in-ssms.md) </span></span>  
 [<span data-ttu-id="9cdb9-141">Modélisation tabulaire &#40;la&#41;tabulaire SSAS</span><span class="sxs-lookup"><span data-stu-id="9cdb9-141">Tabular Modeling &#40;SSAS Tabular&#41;</span></span>](../../tabular-models/tabular-models-ssas.md)  
  
  
