---
title: Enregistrer un rapport dans une bibliothèque SharePoint (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4daa1eee-78b7-43d0-8b22-4a98e8fa66ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49878a0d7115a11e804382cb5139aa0ec7b3d254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605225"
---
# <a name="save-a-report-to-a-sharepoint-library-report-builder"></a><span data-ttu-id="40440-102">Enregistrer un rapport dans une bibliothèque SharePoint (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="40440-102">Save a Report to a SharePoint Library (Report Builder)</span></span>
  <span data-ttu-id="40440-103">Pour enregistrer un rapport sur un serveur de rapports configuré pour une intégration SharePoint, vous devez accéder au serveur SharePoint et établir une connexion au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="40440-103">To save a report to a report server configured for SharePoint integration, you must browse to the SharePoint server and establish a connection to the report server.</span></span> <span data-ttu-id="40440-104">Dans la définition de rapport, toutes les références aux éléments associés au rapport doivent utiliser des valeurs spécifiques à un serveur de rapports SharePoint.</span><span class="sxs-lookup"><span data-stu-id="40440-104">In the report definition, all references to items related to the report must use values that are specific to a SharePoint report server.</span></span> <span data-ttu-id="40440-105">Les éléments associés peuvent consister en des sous-rapports, des rapports d'extraction et des ressources telles que des images Web.</span><span class="sxs-lookup"><span data-stu-id="40440-105">Related items include subreports, drillthrough reports, and resources such as Web-based images.</span></span> <span data-ttu-id="40440-106">Pour plus d’informations, consultez [Spécification de chemins d’accès à des éléments externes &#40;Générateur de rapports et SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="40440-106">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="40440-107">Vous devez avoir l’autorisation de **Membre** ou de **Propriétaire** sur le site SharePoint pour définir les propriétés du projet.</span><span class="sxs-lookup"><span data-stu-id="40440-107">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span>  
  
### <a name="to-save-a-report-to-a-sharepoint-site"></a><span data-ttu-id="40440-108">Pour enregistrer un rapport sur un site SharePoint</span><span class="sxs-lookup"><span data-stu-id="40440-108">To save a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="40440-109">À partir du bouton Générateur de rapports, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="40440-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="40440-110">La boîte de dialogue **Enregistrer sous** _\<Report Item>_ s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="40440-110">The **Save As**_\<Report Item>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="40440-111">Si vous réenregistrez un rapport, il est automatiquement stocké à son emplacement précédent.</span><span class="sxs-lookup"><span data-stu-id="40440-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="40440-112">Utilisez l’option **Enregistrer sous** pour modifier l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="40440-112">Use the **Save As** option to change location.</span></span>  
  
2.  <span data-ttu-id="40440-113">Cliquez éventuellement sur **Sites et serveurs récents** pour afficher une liste de serveurs de rapports et de sites SharePoint récemment utilisés.</span><span class="sxs-lookup"><span data-stu-id="40440-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="40440-114">Accédez au site SharePoint, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="40440-114">Browse to the SharePoint site, and then click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="40440-115">Si vous n'enregistrez pas un rapport ayant subi des modifications dans un délai de 10 heures, il est déconnecté du serveur sans être enregistré.</span><span class="sxs-lookup"><span data-stu-id="40440-115">If you leave a changed report for more than 10 hours without saving it, it is disconnected from the server without being saved.</span></span> <span data-ttu-id="40440-116">Dans ce cas, dans la barre d’état inférieure droite, cliquez sur **Déconnecter**, puis sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="40440-116">If that happens, in the lower-right status bar, click **Disconnect**, and then click **Connect**.</span></span> <span data-ttu-id="40440-117">Le serveur le plus récent figurera dans la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="40440-117">The most recent server will be in the list of available servers.</span></span> <span data-ttu-id="40440-118">Sélectionnez-le pour que le rapport soit à nouveau connecté.</span><span class="sxs-lookup"><span data-stu-id="40440-118">Select it and the report will reconnect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40440-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40440-119">See Also</span></span>  
 [<span data-ttu-id="40440-120">Recherche, affichage et gestion de rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="40440-120">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
