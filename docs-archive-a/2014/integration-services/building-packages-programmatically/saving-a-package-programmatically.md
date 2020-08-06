---
title: Enregistrement d’un package par programmation | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically saving a package
- saving a package programmatically
ms.assetid: 4204f817-d5df-475a-9338-d7f01305d566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2879c4213b2c9c0bf395c103de0d1bc37e4daab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603591"
---
# <a name="saving-a-package-programmatically"></a><span data-ttu-id="4a467-102">Enregistrement d'un package par programme</span><span class="sxs-lookup"><span data-stu-id="4a467-102">Saving a Package Programmatically</span></span>
  <span data-ttu-id="4a467-103">Après avoir généré un package par programme, ou modifié un package existant, vous souhaitez généralement enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="4a467-103">After building a new package programmatically, or modifying an existing one, you usually want to save your changes.</span></span>  
  
 <span data-ttu-id="4a467-104">Toutes les méthodes de cette rubrique qui permettent d'enregistrer des packages requièrent une référence à l'assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="4a467-104">All of the methods used in this topic to save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="4a467-105">Après avoir ajouté la référence dans un nouveau projet, importez l' <xref:Microsoft.SqlServer.Dts.Runtime> espace de noms avec une `using` `Imports` instruction ou.</span><span class="sxs-lookup"><span data-stu-id="4a467-105">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="saving-a-package-programmatically"></a><span data-ttu-id="4a467-106">Enregistrement d'un package par programme</span><span class="sxs-lookup"><span data-stu-id="4a467-106">Saving a Package Programmatically</span></span>  
 <span data-ttu-id="4a467-107">Pour enregistrer un package programmatiquement, appelez l’une des méthodes suivantes de la classe [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  <xref:Microsoft.SqlServer.Dts.Runtime.Application> :</span><span class="sxs-lookup"><span data-stu-id="4a467-107">To save a package programmatically, call one of the following methods of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application> class:</span></span>  
  
|<span data-ttu-id="4a467-108">Emplacement de stockage</span><span class="sxs-lookup"><span data-stu-id="4a467-108">Storage Location</span></span>|<span data-ttu-id="4a467-109">Méthode à appeler</span><span class="sxs-lookup"><span data-stu-id="4a467-109">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="4a467-110">Fichier</span><span class="sxs-lookup"><span data-stu-id="4a467-110">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToXml%2A>|  
|<span data-ttu-id="4a467-111">Magasin de packages SSIS</span><span class="sxs-lookup"><span data-stu-id="4a467-111">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServer%2A><br /><br /> <span data-ttu-id="4a467-112">or</span><span class="sxs-lookup"><span data-stu-id="4a467-112">or</span></span><br /><br /> <xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServerAs%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4a467-113">Les méthodes de la classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> qui permettent d'utiliser le magasin de packages SSIS prennent uniquement en charge « . » ou le nom du serveur local.</span><span class="sxs-lookup"><span data-stu-id="4a467-113">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support "." or the server name for the local server.</span></span> <span data-ttu-id="4a467-114">Vous ne pouvez pas utiliser « (local) » ou « localhost ».</span><span class="sxs-lookup"><span data-stu-id="4a467-114">You cannot use "(local)" or "localhost".</span></span>  
  
<span data-ttu-id="4a467-115">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4a467-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4a467-116">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="4a467-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4a467-117">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="4a467-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4a467-118">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="4a467-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a467-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a467-119">See Also</span></span>  
 [<span data-ttu-id="4a467-120">Enregistrer des packages</span><span class="sxs-lookup"><span data-stu-id="4a467-120">Save Packages</span></span>](../save-packages.md)  
  
  
