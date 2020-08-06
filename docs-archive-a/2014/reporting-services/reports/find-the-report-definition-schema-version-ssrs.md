---
title: Rechercher la version du schéma de définition de rapport | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- XML schemas [Reporting Services]
- Report Definition Language, XML schema
- schemas [Reporting Services]
ms.assetid: 67954419-1b61-4481-a3b9-23b4ba7a5624
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 413a270a3722ddda1f418c748fa5b7fba50dfeea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700782"
---
# <a name="find-the-report-definition-schema-version-ssrs"></a><span data-ttu-id="1ea6a-102">Rechercher la version du schéma de définition de rapport (SSRS)</span><span class="sxs-lookup"><span data-stu-id="1ea6a-102">Find the Report Definition Schema Version (SSRS)</span></span>
  <span data-ttu-id="1ea6a-103">Un fichier de définition de rapport spécifie l'espace de noms RDL de la version du schéma de définition de rapport qui est utilisée pour valider le fichier rdl.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-103">A report definition file specifies the RDL namespace for the version of the report definition schema that is used to validate the rdl file.</span></span> <span data-ttu-id="1ea6a-104">Lorsque vous ouvrez un fichier .rdl dans un environnement de création de rapports, tel que le Concepteur de rapports de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou le Générateur de rapports, si le rapport a déjà été créé pour un espace de noms, un fichier de sauvegarde est automatiquement créé et le rapport est mis à niveau d'après l'espace de noms actuel.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-104">When you open an .rdl file in a report authoring environment such as Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or Report Builder, if the report was created for a previous namespace, a backup file is automatically created, and the report is upgraded to the current namespace.</span></span> <span data-ttu-id="1ea6a-105">Si vous enregistrez la définition de rapport mise à niveau, vous enregistrez le fichier .rdl converti.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-105">If you save the upgraded report definition, you have saved the converted .rdl file.</span></span> <span data-ttu-id="1ea6a-106">Il s'agit de la seule façon de mettre à niveau une définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-106">This is the only way to upgrade a report definition.</span></span> <span data-ttu-id="1ea6a-107">La définition de rapport proprement dite n'est pas mise à niveau sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-107">The report definition itself is not upgraded on a report server.</span></span> <span data-ttu-id="1ea6a-108">Le rapport compilé est mis à niveau sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-108">The compiled report is upgraded on a report server.</span></span> <span data-ttu-id="1ea6a-109">Pour plus d'informations, consultez [Mettre à niveau des rapports](../install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="1ea6a-109">For more information, see [Upgrade Reports](../install-windows/upgrade-reports.md).</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-a-report"></a><span data-ttu-id="1ea6a-110">Procédure : identifier la version du schéma RDL d'un rapport</span><span class="sxs-lookup"><span data-stu-id="1ea6a-110">How to: Identify the RDL Schema Version of a Report</span></span>  
  
1.  <span data-ttu-id="1ea6a-111">Ouvrez le fichier de rapport .rdl dans une application, telle que le Bloc-notes ou XML Notepad 2007, dans laquelle vous pouvez visualiser le fichier xml.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-111">Open the report .rdl file in an application such as Notepad or XML Notepad 2007 in which you can view the xml.</span></span>  
  
     <span data-ttu-id="1ea6a-112">L'élément de rapport XML indique l'espace de noms du schéma.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-112">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="1ea6a-113">Par exemple, l'élément de rapport suivant indique l'espace de noms pour le Concepteur de rapports et l'espace de noms pour la définition du rapport.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-113">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="1ea6a-114">L'espace de noms de la définition de rapport est spécifié par l'URL suivante : `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-114">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-report-designer"></a><span data-ttu-id="1ea6a-115">Procédure : identifier la version du schéma RDL du Concepteur de rapports</span><span class="sxs-lookup"><span data-stu-id="1ea6a-115">How to: Identify the RDL Schema Version of Report Designer</span></span>  
  
1.  <span data-ttu-id="1ea6a-116">Ouvrez un nouveau projet.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-116">Open a new project.</span></span> <span data-ttu-id="1ea6a-117">La version du projet que vous choisissez détermine la version du schéma RDL.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-117">The version of the project that you choose determines the version of the RDL schema.</span></span> <span data-ttu-id="1ea6a-118">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], plusieurs versions de schéma sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-118">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], more than one schema version is supported.</span></span> <span data-ttu-id="1ea6a-119">Pour plus d’informations, consultez [Déploiement et prise en charge des versions dans les outils de données SQL Server &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1ea6a-119">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="1ea6a-120">Dans le menu **Projet** , cliquez sur **Ajouter un nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-120">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="1ea6a-121">La boîte de dialogue **Ajouter un nouvel élément** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-121">The **Add New Item** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="1ea6a-122">Dans le volet **Modèles** , cliquez sur **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-122">In the **Templates** pane, click **Report**.</span></span>  
  
4.  <span data-ttu-id="1ea6a-123">Dans la zone **Nom**, tapez un nom de rapport ou acceptez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-123">In **Name**, type a report name or accept the default.</span></span>  
  
5.  <span data-ttu-id="1ea6a-124">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-124">Click **Add**.</span></span> <span data-ttu-id="1ea6a-125">Le Concepteur de rapports ouvre un rapport vide en mode Création.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-125">Report Designer opens a new blank report in Design view.</span></span>  
  
6.  <span data-ttu-id="1ea6a-126">Dans le menu **Affichage** , cliquez sur **Code**.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-126">On the **View** menu, click **Code**.</span></span> <span data-ttu-id="1ea6a-127">La définition du rapport s'affiche sous forme de fichier XML.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-127">The report definition is displayed as an XML file.</span></span>  
  
     <span data-ttu-id="1ea6a-128">L'élément de rapport XML indique l'espace de noms du schéma.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-128">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="1ea6a-129">Par exemple, l'élément de rapport suivant indique l'espace de noms pour le Concepteur de rapports et l'espace de noms pour la définition du rapport.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-129">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner  
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="1ea6a-130">L'espace de noms de la définition de rapport est spécifié par l'URL suivante : `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="1ea6a-130">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-on-the-report-server"></a><span data-ttu-id="1ea6a-131">Procédure : identifier la version du schéma RDL sur Report Server</span><span class="sxs-lookup"><span data-stu-id="1ea6a-131">How to: Identify the RDL Schema Version on the Report Server</span></span>  
  
-   <span data-ttu-id="1ea6a-132">Dans le Gestionnaire de rapports, tapez l'URL du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-132">In Report Manager, type the URL for the report server.</span></span> <span data-ttu-id="1ea6a-133">Par exemple, l'URL suivante spécifie un serveur de rapports sur l'ordinateur local :</span><span class="sxs-lookup"><span data-stu-id="1ea6a-133">For example, the following URL specifies a report server on the local computer:</span></span>  
  
     `http://localhost/reportserver/reportdefinition.xsd`  
  
     <span data-ttu-id="1ea6a-134">Le fichier .xsd s'ouvre dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-134">The .xsd file opens in the browser.</span></span>  
  
     <span data-ttu-id="1ea6a-135">L'élément de schéma XML indique l'espace de noms du schéma.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-135">The XML schema element specifies the schema namespace.</span></span> <span data-ttu-id="1ea6a-136">Par exemple, l’élément de schéma suivant indique trois espaces de noms : la référence targetNamespace utilisée en interne par [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], la référence xsd pour le schéma lui-même (xsd) et la référence de définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="1ea6a-136">For example, the following schema element specifies three namespaces: the targetNamespace reference that is used internally by [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], the xsd reference for the schema itself (xsd), and the report definition reference.</span></span>  
  
    ```  
    <xsd:schema   
    targetNamespace="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    elementFormDefault="qualified">  
    ```  
  
     <span data-ttu-id="1ea6a-137">L'espace de noms de la définition de rapport est spécifié par l'URL suivante : `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="1ea6a-137">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea6a-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ea6a-138">See Also</span></span>  
 <span data-ttu-id="1ea6a-139">[Rapports de mise à niveau](../install-windows/upgrade-reports.md) </span><span class="sxs-lookup"><span data-stu-id="1ea6a-139">[Upgrade Reports](../install-windows/upgrade-reports.md) </span></span>  
 [<span data-ttu-id="1ea6a-140">RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1ea6a-140">Report Definition Language &#40;SSRS&#41;</span></span>](report-definition-language-ssrs.md)  
  
  
