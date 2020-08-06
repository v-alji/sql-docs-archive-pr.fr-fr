---
title: Implémentation d’une extension de remise | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery [Reporting Services]
- custom delivery extensions [Reporting Services]
- extensions [Reporting Services], delivery
- delivery extensions [Reporting Services]
ms.assetid: 600cd229-efcd-480e-8c95-3c3c39ff4e7a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af1e804e029dae77fb7836577aa8d4a45ad20109
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615044"
---
# <a name="implementing-a-delivery-extension"></a><span data-ttu-id="af191-102">Implémentation d'une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-102">Implementing a Delivery Extension</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="af191-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permet aux utilisateurs de créer et de publier des rapports qui, une fois créés et publiés, peuvent être remis à différents emplacements.</span><span class="sxs-lookup"><span data-stu-id="af191-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enables users to create and publish reports that, once created and published, can be delivered to various locations.</span></span> <span data-ttu-id="af191-104">De plus, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclut plusieurs extensions de remise et une API de remise qui permettent aux développeurs de créer des extensions de remise supplémentaires pour étendre les fonctionnalités de remise proposées dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af191-104">In addition, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes several delivery extensions and a delivery API that enable developers to create additional delivery extensions to further extend the functionality of delivery in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="af191-105">Pour un exemple d’implémentation d’extension de remise, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="af191-105">For a sample implementation of a delivery extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af191-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="af191-106">In This Section</span></span>  
 <span data-ttu-id="af191-107">[Présentation des extensions de remise] Delivery-extensions-overview.md)</span><span class="sxs-lookup"><span data-stu-id="af191-107">[Delivery Extensions Overview]delivery-extensions-overview.md)</span></span>  
 <span data-ttu-id="af191-108">Explique comment écrire une extension de remise personnalisée pour [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af191-108">Introduces how to write a custom delivery extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="af191-109">Préparation pour la mise en œuvre d'une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-109">Preparing to Implement a Delivery Extension</span></span>](preparing-to-implement-a-delivery-extension.md)  
 <span data-ttu-id="af191-110">Décrit les interfaces et les classes disponibles lors de l'implémentation d'une extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], ainsi que les problèmes à prendre en considération avant l'implémentation.</span><span class="sxs-lookup"><span data-stu-id="af191-110">Describes the interfaces and classes available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, as well as issues to consider before implementation.</span></span>  
  
 [<span data-ttu-id="af191-111">Création d'une bibliothèque d'extensions de remise</span><span class="sxs-lookup"><span data-stu-id="af191-111">Creating a Delivery Extension Library</span></span>](creating-a-delivery-extension-library.md)  
 <span data-ttu-id="af191-112">Décrit comment assigner un espace de noms à votre extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] et comment compiler votre extension de remise dans une DLL de bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="af191-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension and compiling your delivery extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="af191-113">Mise en œuvre de l'interface IDeliveryExtension pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-113">Implementing the IDeliveryExtension Interface for a Delivery Extension</span></span>](implementing-the-ideliveryextension-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="af191-114">Décrit les attributs d'une extension de remise et comment implémenter votre propre classe d'extension de remise.</span><span class="sxs-lookup"><span data-stu-id="af191-114">Describes the attributes of a delivery extension, and how to implement your own delivery extension class.</span></span>  
  
 [<span data-ttu-id="af191-115">Utilisation d'une classe de notification pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-115">Using a Notification Class for a Delivery Extension</span></span>](using-a-notification-class-for-a-delivery-extension.md)  
 <span data-ttu-id="af191-116">Décrit les attributs d’une classe **Notification** et comment l’utiliser dans l’implémentation de votre extension de remise.</span><span class="sxs-lookup"><span data-stu-id="af191-116">Describes the attributes of a **Notification** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="af191-117">Utilisation de la classe Paramètre pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-117">Using the Setting Class for a Delivery Extension</span></span>](using-the-setting-class-for-a-delivery-extension.md)  
 <span data-ttu-id="af191-118">Décrit les attributs d’une classe **Setting** et comment l’utiliser dans l’implémentation de votre extension de remise.</span><span class="sxs-lookup"><span data-stu-id="af191-118">Describes the attributes of a **Setting** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="af191-119">Utilisation de l'interface IDeliveryReportServerInformation pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-119">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="af191-120">Décrit les attributs d’une interface **IDeliveryReportServerInformation** et comment l’utiliser dans l’implémentation de votre extension de remise.</span><span class="sxs-lookup"><span data-stu-id="af191-120">Describes the attributes of a **IDeliveryReportServerInformation** interface and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="af191-121">Utilisation de la classe Report pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-121">Using the Report Class for a Delivery Extension</span></span>](using-the-report-class-for-a-delivery-extension.md)  
 <span data-ttu-id="af191-122">Décrit les attributs d’une classe **Report** et comment l’utiliser dans l’implémentation de votre extension de remise.</span><span class="sxs-lookup"><span data-stu-id="af191-122">Describes the attributes of a **Report** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="af191-123">Utilisation de la classe RenderedOutputFile pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-123">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
 <span data-ttu-id="af191-124">Décrit les attributs d’une classe **RenderedOutputFile** et comment l’utiliser dans l’implémentation de votre extension de remise.</span><span class="sxs-lookup"><span data-stu-id="af191-124">Describes the attributes of a **RenderedOutputFile** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="af191-125">Implémentation de l'interface ISubscriptionBaseUIUserControl pour une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-125">Implementing the ISubscriptionBaseUIUserControl Interface for a Delivery Extension</span></span>](implementing-the-isubscriptionbaseuiusercontrol-interface.md)  
 <span data-ttu-id="af191-126">Décrit les attributs d'un contrôle utilisateur d'extension de remise et comment implémenter votre propre interface utilisateur pour un abonnement.</span><span class="sxs-lookup"><span data-stu-id="af191-126">Describes the attributes of a delivery extension user control and how to implement your own user interface for a subscription.</span></span>  
  
 [<span data-ttu-id="af191-127">Déploiement d'une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-127">Deploying a Delivery Extension</span></span>](deploying-a-delivery-extension.md)  
 <span data-ttu-id="af191-128">Décrit comment déployer votre extension de remise.</span><span class="sxs-lookup"><span data-stu-id="af191-128">Describes how to deploy your delivery extension.</span></span>  
  
 [<span data-ttu-id="af191-129">Débogage du code d'extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-129">Debugging Delivery Extension Code</span></span>](debugging-delivery-extension-code.md)  
 <span data-ttu-id="af191-130">Décrit comment déboguer le code dans votre extension de remise.</span><span class="sxs-lookup"><span data-stu-id="af191-130">Describes how to debug code in your delivery extension.</span></span>  
  
 [<span data-ttu-id="af191-131">Suppression d'une extension de remise</span><span class="sxs-lookup"><span data-stu-id="af191-131">Removing a Delivery Extension</span></span>](removing-a-delivery-extension.md)  
 <span data-ttu-id="af191-132">Décrit comment supprimer une extension de remise d'un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="af191-132">Describes how to remove a delivery extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af191-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af191-133">See Also</span></span>  
 <span data-ttu-id="af191-134">[Extensions de Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="af191-134">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="af191-135">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="af191-135">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
