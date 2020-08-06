---
title: Impossible de charger le fichier ou l’assembly &#39;Microsoft. Data. services, version = 3.5.0.0, culture = neutral, PublicKeyToken = b77a5c561934e089&#39; ou l’une de ses dépendances. Le système ne peut pas trouver le fichier spécifié. | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 81ed0f44-8782-462d-af8f-0ba5b975df27
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f9eed7ad90c1e720d07c714e351c24ae6657717
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612539"
---
# <a name="could-not-load-file-or-assembly-39microsoftdataservices-version3500-cultureneutral-publickeytokenb77a5c561934e08939-or-one-of-its-dependencies-the-system-cannot-find-the-file-specified"></a><span data-ttu-id="f0d2e-104">Impossible de charger le fichier ou l’assembly &#39;Microsoft. Data. services, version = 3.5.0.0, culture = neutral, PublicKeyToken = b77a5c561934e089&#39; ou l’une de ses dépendances.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-104">Could not load file or assembly &#39;Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089&#39; or one of its dependencies.</span></span> <span data-ttu-id="f0d2e-105">Le système ne peut pas trouver le fichier spécifié.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-105">The system cannot find the file specified.</span></span>
  <span data-ttu-id="f0d2e-106">Dans les environnements SharePoint 2010 qui disposent de PowerPivot pour SharePoint, cette erreur se produira si vous tentez une exportation de flux de données et que la version requise de Microsoft ADO.NET Data Services n'est pas disponible sur le système.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-106">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if you attempt a data feed export and the system is missing the required version of Microsoft ADO.NET Data Services.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0d2e-107">Détails</span><span class="sxs-lookup"><span data-stu-id="f0d2e-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0d2e-108">S’applique à</span><span class="sxs-lookup"><span data-stu-id="f0d2e-108">Applies to</span></span>|<span data-ttu-id="f0d2e-109">PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="f0d2e-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="f0d2e-110">Version du produit</span><span class="sxs-lookup"><span data-stu-id="f0d2e-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="f0d2e-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0d2e-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="f0d2e-112">Cause</span><span class="sxs-lookup"><span data-stu-id="f0d2e-112">Cause</span></span>|<span data-ttu-id="f0d2e-113">ADO.NET Data Services 3.5 SP1 est introuvable.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-113">ADO.NET Data Services 3.5 SP1 was not found.</span></span>|  
|<span data-ttu-id="f0d2e-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f0d2e-114">Message Text</span></span>|<span data-ttu-id="f0d2e-115">Impossible de charger le fichier ou l'assembly 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' ou une de ses dépendances.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-115">Could not load file or assembly 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies.</span></span> <span data-ttu-id="f0d2e-116">Le système ne trouve pas le fichier spécifié.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-116">The system cannot find the file specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f0d2e-117">Explication</span><span class="sxs-lookup"><span data-stu-id="f0d2e-117">Explanation</span></span>  
 <span data-ttu-id="f0d2e-118">SharePoint 2010 inclut un bouton Exporter en tant que flux que vous pouvez utiliser pour exporter une liste SharePoint en tant que flux de données XML.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-118">SharePoint 2010 includes an Export as Data Feed button that you can use to export a SharePoint list as an XML data feed.</span></span> <span data-ttu-id="f0d2e-119">De plus, Reporting Services en mode SharePoint et PowerPivot pour SharePoint prennent tous les deux en charge les fonctionnalités de flux requises par ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-119">In addition, both Reporting Services in SharePoint mode and PowerPivot for SharePoint support data feed features that require ADO.NET Data Services.</span></span>  
  
 <span data-ttu-id="f0d2e-120">Si ADO.NET Data Services n'est pas installé, cette erreur se produira lorsque vous demanderez un flux.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-120">If ADO.NET Data Services is not installed, this error will occur when you request a data feed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0d2e-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f0d2e-121">User Action</span></span>  
  
1.  <span data-ttu-id="f0d2e-122">Accédez à la documentation relative à la configuration matérielle et logicielle requise pour SharePoint 2010, [déterminer la configuration matérielle et logicielle requise (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) ( https://go.microsoft.com/fwlink/?LinkId=169734) .</span><span class="sxs-lookup"><span data-stu-id="f0d2e-122">Go to the hardware and software requirements documentation for SharePoint 2010, [Determine Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) (https://go.microsoft.com/fwlink/?LinkId=169734).</span></span>  
  
2.  <span data-ttu-id="f0d2e-123">Dans **Installer les logiciels requis**, recherchez le lien pour ADO.NET Data Services 3.5 correspondant au système d'exploitation que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-123">In **Installing software prerequisites**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using.</span></span>  
  
3.  <span data-ttu-id="f0d2e-124">Cliquez sur le lien, puis exécutez le programme d'installation qui installe le service.</span><span class="sxs-lookup"><span data-stu-id="f0d2e-124">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d2e-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0d2e-125">See Also</span></span>  
 [<span data-ttu-id="f0d2e-126">Déployer des solutions PowerPivot sur SharePoint</span><span class="sxs-lookup"><span data-stu-id="f0d2e-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
