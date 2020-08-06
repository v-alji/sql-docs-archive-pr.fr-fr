---
title: Déploiement d’une extension pour le traitement des données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: e5c0b5a9-1386-47cb-aade-96653ecfaa54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84fc2d2853ce7a6aae77f313ef0f4026ad2f35cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708964"
---
# <a name="deploying-a-data-processing-extension"></a><span data-ttu-id="3160a-102">Déploiement d'une extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="3160a-102">Deploying a Data Processing Extension</span></span>
  <span data-ttu-id="3160a-103">Une fois que vous avez écrit et compilé votre extension pour le traitement des données [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] dans une bibliothèque [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], vous devez la rendre détectable par le serveur de rapports et par le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3160a-103">Once you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you need to make it discoverable by the report server and by Report Designer.</span></span> <span data-ttu-id="3160a-104">Cette opération est aussi simple que de copier l'extension vers les répertoires appropriés et d'ajouter des entrées aux fichiers de configuration [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] appropriés.</span><span class="sxs-lookup"><span data-stu-id="3160a-104">This is as easy as copying the extension to the appropriate directories and adding entries to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="3160a-105">Élément Extension du fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="3160a-105">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="3160a-106">Les extensions pour le traitement des données que vous déployez sur le serveur de rapports ou le Concepteur de rapports doivent être entrées en tant qu’éléments **Extension** dans les fichiers de configuration.</span><span class="sxs-lookup"><span data-stu-id="3160a-106">Data processing extensions that you deploy to the report server or Report Designer need to be entered as **Extension** elements in the configuration files.</span></span> <span data-ttu-id="3160a-107">Ces fichiers sont RSReportServer.config pour le serveur de rapports et RSReportDesigner.config pour le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3160a-107">These files are RSReportServer.config for the report server and RSReportDesigner.config for Report Designer.</span></span>  
  
 <span data-ttu-id="3160a-108">Le tableau suivant décrit les attributs de l’élément **Extension** pour les extensions pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="3160a-108">The following table describes the attributes for the **Extension** element for data processing extensions.</span></span>  
  
|<span data-ttu-id="3160a-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="3160a-109">Attribute</span></span>|<span data-ttu-id="3160a-110">Description</span><span class="sxs-lookup"><span data-stu-id="3160a-110">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="3160a-111">Nom unique de l'extension, par exemple, « SQL » pour l'extension pour le traitement des données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou « OLEDB » pour l'extension pour le traitement des données OLE DB.</span><span class="sxs-lookup"><span data-stu-id="3160a-111">A unique name for the extension, for example, "SQL" for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data processing extension or "OLEDB" for the OLE DB data processing extension.</span></span> <span data-ttu-id="3160a-112">La longueur maximale de l'attribut `Name` s'élève à 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="3160a-112">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="3160a-113">Le nom doit être unique au sein de toutes les entrées de l’élément **Extension** d’un fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="3160a-113">The name must be unique among all entries within the **Extension** element of a configuration file.</span></span>|  
|`Type`|<span data-ttu-id="3160a-114">Liste séparée par des virgules qui inclut l'espace de noms complet, ainsi que le nom de l'assembly.</span><span class="sxs-lookup"><span data-stu-id="3160a-114">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="3160a-115">La valeur `false` indique que l'extension pour le traitement des données ne doit pas être visible dans les interfaces utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3160a-115">A value of `false` indicates that the data processing extension should not be visible in user interfaces.</span></span> <span data-ttu-id="3160a-116">Si cet attribut n'est pas défini, la valeur par défaut est `true`.</span><span class="sxs-lookup"><span data-stu-id="3160a-116">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="3160a-117">Pour plus d’informations sur les fichiers RSReportServer.config ou RSReportDesigner.config, consultez [Fichiers de configuration de Reporting Services](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="3160a-117">For more information about the RSReportServer.config or RSReportDesigner.config files, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3160a-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3160a-118">In This Section</span></span>  
  
|<span data-ttu-id="3160a-119">Rubrique</span><span class="sxs-lookup"><span data-stu-id="3160a-119">Topic</span></span>|<span data-ttu-id="3160a-120">Description</span><span class="sxs-lookup"><span data-stu-id="3160a-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3160a-121">Procédure : déployer une extension pour le traitement des données sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="3160a-121">How to: Deploy a Data Processing Extension to a Report Server</span></span>](deploying-a-data-processing-extension-to-a-report-server.md)|<span data-ttu-id="3160a-122">Décrit comment déployer votre extension pour le traitement des données sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3160a-122">Describes how to deploy your data processing extension to a report server.</span></span>|  
|[<span data-ttu-id="3160a-123">Procédure : déployer une extension pour le traitement des données sur le Concepteur de rapports</span><span class="sxs-lookup"><span data-stu-id="3160a-123">How to: Deploy a Data Processing Extension to Report Designer</span></span>](deploying-a-data-processing-extension-to-report-designer.md)|<span data-ttu-id="3160a-124">Décrit comment déployer votre extension pour le traitement des données sur le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3160a-124">Describes how to deploy your data processing extension to Report Designer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3160a-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3160a-125">See Also</span></span>  
 <span data-ttu-id="3160a-126">[Extensions de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="3160a-126">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="3160a-127">[Implémentation d’une extension pour le traitement des données](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="3160a-127">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="3160a-128">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3160a-128">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
