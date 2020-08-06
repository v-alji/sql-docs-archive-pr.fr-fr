---
title: Paramètres de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, parameters
ms.assetid: b1bb3ea3-8097-4e76-b9c2-78a0f46a23bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 76a5ebe7018fdc58f02a4d2454d40f172c752c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708087"
---
# <a name="integration-services-parameters"></a><span data-ttu-id="ade6c-102">Paramètres Integration Services</span><span class="sxs-lookup"><span data-stu-id="ade6c-102">Integration Services Parameters</span></span>
  <span data-ttu-id="ade6c-103">Pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , vous pouvez décider d’analyser [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] des packages sur l’ordinateur ou des [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fichiers de package dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ade6c-103">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you can decide to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer, or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package files in the file system.</span></span> <span data-ttu-id="ade6c-104">Si vous analysez des fichiers dans le système de fichiers, fournissez un chemin d'accès au dossier qui contient les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade6c-104">If you analyze files in the file system, provide a path to the folder that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ade6c-105">Options</span><span class="sxs-lookup"><span data-stu-id="ade6c-105">Options</span></span>  
 <span data-ttu-id="ade6c-106">**Analyser les packages SSIS sur l'ordinateur**</span><span class="sxs-lookup"><span data-stu-id="ade6c-106">**Analyze SSIS packages on Computer**</span></span>  
 <span data-ttu-id="ade6c-107">Sélectionnez cette option pour analyser les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ade6c-107">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer.</span></span> <span data-ttu-id="ade6c-108">Cette option est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="ade6c-108">By default, this option is selected.</span></span>  
  
 <span data-ttu-id="ade6c-109">**Analyser les fichiers de package SSIS**</span><span class="sxs-lookup"><span data-stu-id="ade6c-109">**Analyze SSIS package files**</span></span>  
 <span data-ttu-id="ade6c-110">Sélectionnez cette option pour analyser les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ade6c-110">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages in the file system.</span></span>  
  
 <span data-ttu-id="ade6c-111">**Chemin d'accès aux packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="ade6c-111">**Path to SSIS packages**</span></span>  
 <span data-ttu-id="ade6c-112">Recherchez un chemin UNC ou un chemin local qui contient vos packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ade6c-112">Locate a UNC or local path that holds your [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="ade6c-113">Il est inutile d'inclure les noms de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ade6c-113">You do not have to include file names.</span></span> <span data-ttu-id="ade6c-114">Si le chemin d’accès que vous avez entré est inaccessible, vous ne pouvez pas cliquer sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ade6c-114">If the path you have entered cannot be accessed, you cannot click **Next**.</span></span> <span data-ttu-id="ade6c-115">Par défaut, le chemin d’accès est vide.</span><span class="sxs-lookup"><span data-stu-id="ade6c-115">By default, the path is blank.</span></span> <span data-ttu-id="ade6c-116">Ce champ est activé uniquement lorsque vous sélectionnez **analyser les fichiers de package SSIS**.</span><span class="sxs-lookup"><span data-stu-id="ade6c-116">This field is enabled only when you select **Analyze SSIS package files**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade6c-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ade6c-117">See Also</span></span>  
 <span data-ttu-id="ade6c-118">[Utilisation du conseiller de mise à niveau](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="ade6c-118">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="ade6c-119">Guide de référence de l'interface utilisateur du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ade6c-119">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
