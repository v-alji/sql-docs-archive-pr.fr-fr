---
title: Suppression d’une extension de remise | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- removing delivery extensions
- deleting delivery extensions
- delivery extensions [Reporting Services], removing
ms.assetid: dcb7caf2-d19a-4bc5-afb3-2b61ad11cac5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c4320f46b5013b0fa2accbc81792748c2d9f384
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615036"
---
# <a name="removing-a-delivery-extension"></a><span data-ttu-id="80876-102">Suppression d'une extension de remise</span><span class="sxs-lookup"><span data-stu-id="80876-102">Removing a Delivery Extension</span></span>
  <span data-ttu-id="80876-103">Pour supprimer une extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], supprimez simplement l’élément **Extension** de votre extension de remise du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="80876-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, simply remove the **Extension** element for your delivery extension from the configuration file.</span></span> <span data-ttu-id="80876-104">Une fois les informations de configuration supprimées, l'extension de remise n'est plus disponible pour le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="80876-104">After the configuration information is removed, the delivery extension is no longer available to the report server.</span></span>  
  
 <span data-ttu-id="80876-105">Une fois que l’élément **Extension** correspondant d’une extension de remise est supprimé du fichier de configuration, il n’est plus inscrit auprès du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="80876-105">Once a delivery extension's corresponding **Extension** element is removed from the configuration file, it is no longer registered with the report server.</span></span> <span data-ttu-id="80876-106">Le serveur de rapports supprime l'entrée dans la liste d'extensions de remise et désactive tous les abonnements qui utilisent cette extension de remise.</span><span class="sxs-lookup"><span data-stu-id="80876-106">The report server removes the entry from the list of delivery extensions and deactivates any subscriptions which use that delivery extension.</span></span> <span data-ttu-id="80876-107">Lorsqu'une extension de remise est supprimée, les utilisateurs ne sont plus en mesure de le sélectionner comme méthode de notification.</span><span class="sxs-lookup"><span data-stu-id="80876-107">When a delivery extension is removed, users are no longer able to select it as a method of notification.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80876-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80876-108">See Also</span></span>  
 <span data-ttu-id="80876-109">[Implémentation d’une extension de remise](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="80876-109">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="80876-110">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="80876-110">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
