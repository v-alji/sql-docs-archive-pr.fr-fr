---
title: Utilisation de la classe Setting pour une extension de remise | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], settings
- Setting class
ms.assetid: 50746639-da7c-46a5-ac7b-e87dd6b91880
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 594cf28391ae4523e1a95ad79ee5b1280ff72218
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696487"
---
# <a name="using-the-setting-class-for-a-delivery-extension"></a><span data-ttu-id="c59d2-102">Utilisation de la classe Setting pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="c59d2-102">Using the Setting Class for a Delivery Extension</span></span>
  <span data-ttu-id="c59d2-103">La classe <xref:Microsoft.ReportingServices.Interfaces.Setting> se trouve dans l'espace de noms <xref:Microsoft.ReportingServices.Interfaces> et représente les informations relatives aux paramètres d'une extension de remise.</span><span class="sxs-lookup"><span data-stu-id="c59d2-103">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is located in the <xref:Microsoft.ReportingServices.Interfaces> namespace and represents information about extension settings for a delivery extension.</span></span> <span data-ttu-id="c59d2-104">La classe <xref:Microsoft.ReportingServices.Interfaces.Setting> fournit l'infrastructure de stockage des informations sur les paramètres nécessaires au bon fonctionnement d'une extension de remise.</span><span class="sxs-lookup"><span data-stu-id="c59d2-104">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class provides infrastructure for storing information about the settings that are required in order for a delivery extension to function properly.</span></span> <span data-ttu-id="c59d2-105">Par exemple, dans l'extension de remise par messagerie du serveur de rapports, un utilisateur est tenu de fournir des paramètres spécifiques à la remise par messagerie, tels que l'adresse du destinataire, l'adresse de l'expéditeur ou la ligne d'objet du message électronique.</span><span class="sxs-lookup"><span data-stu-id="c59d2-105">For example, in Report Server E-Mail delivery, a user is required to supply settings specific to e-mail delivery, such as the recipient's address, the sender's address, the subject line of the e-mail, and more.</span></span> <span data-ttu-id="c59d2-106">Vos fournisseurs de remise personnalisés demanderont sans aucun doute à l'utilisateur de fournir des paramètres spécifiques afin que l'extension de remise puisse remettre des notifications et des rapports.</span><span class="sxs-lookup"><span data-stu-id="c59d2-106">Undoubtedly, your custom delivery providers will require the user to supply specific settings in order for the delivery extension to deliver notifications and reports.</span></span>  
  
 <span data-ttu-id="c59d2-107">La classe <xref:Microsoft.ReportingServices.Interfaces.Setting> est utilisée lors de l'implémentation de la propriété <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> de l'interface <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>.</span><span class="sxs-lookup"><span data-stu-id="c59d2-107">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is used when implementing the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> property of the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface.</span></span> <span data-ttu-id="c59d2-108">La classe <xref:Microsoft.ReportingServices.Interfaces.Setting> est également utilisée pour traiter les données de paramètre d'extension fournies par un utilisateur lorsqu'un abonnement ou la notification est créé(e).</span><span class="sxs-lookup"><span data-stu-id="c59d2-108">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is also used for processing the extension setting data that is supplied by a user when a subscription or notification is created.</span></span>  
  
 <span data-ttu-id="c59d2-109">Pour un exemple d’utilisation de la classe <xref:Microsoft.ReportingServices.Interfaces.Setting>, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="c59d2-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Setting> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c59d2-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c59d2-110">See Also</span></span>  
 <span data-ttu-id="c59d2-111">[Implémentation d’une extension de remise](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="c59d2-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="c59d2-112">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c59d2-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
