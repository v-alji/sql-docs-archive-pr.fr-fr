---
title: Programmation de la boîte de message d’exception | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- ExceptionMessageBox class, about ExceptionMessageBox class
- exception message box [SQL Server], about exception message box
- exception message box [SQL Server]
- interfaces [SQL Server]
- exceptions [SQL Server]
- messages [SQL Server], exception message box
ms.assetid: 0b1ba514-6959-4e69-bfd2-3cf3c1ac4b9c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2425169f838199ce24b4331dd57c74b480adf62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709896"
---
# <a name="exception-message-box-programming"></a><span data-ttu-id="fc5ef-102">Programmation de boîte de message d'exception</span><span class="sxs-lookup"><span data-stu-id="fc5ef-102">Exception Message Box Programming</span></span>
  <span data-ttu-id="fc5ef-103">La boîte de message d’exception est une interface de programmation installée avec et utilisée par les [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] composants graphiques.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-103">The exception message box is a programmatic interface that is installed with and used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] graphical components.</span></span> <span data-ttu-id="fc5ef-104">Il s'agit d'un assembly managé pris en charge que vous pouvez utiliser dans vos applications pour contrôler les messages de manière beaucoup plus rigoureuse et pour donner à vos utilisateurs la possibilité d'enregistrer le contenu des messages d'erreur afin de pouvoir obtenir une assistance ultérieure.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-104">The exception message box is a supported managed assembly that you can use in your applications to provide significantly more control over the messaging experience and to give your users the options to save error message content for later reference and to get help on messages.</span></span> <span data-ttu-id="fc5ef-105">La boîte de message d'exception étant installée par toutes les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'exception de [!INCLUDE[ssEW](../../includes/ssew-md.md)], vous pouvez l'utiliser sans configuration supplémentaire sur tout ordinateur sur lequel les composants clients [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ont été installés.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-105">Because the exception message box is installed by all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssEW](../../includes/ssew-md.md)], you can use it with no additional configuration on any computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client components have been installed.</span></span>  
  
 <span data-ttu-id="fc5ef-106">La classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> dans l'espace de noms <xref:Microsoft.SqlServer.MessageBox> a toutes les fonctionnalités de la classe <xref:System.Windows.Forms.MessageBox>, et davantage encore.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-106">The <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in the <xref:Microsoft.SqlServer.MessageBox> namespace has all the functionality of the <xref:System.Windows.Forms.MessageBox> class and more.</span></span> <span data-ttu-id="fc5ef-107">Idéal pour toutes les tâches pour lesquelles <xref:System.Windows.Forms.MessageBox> peut être utilisé, <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> est conçu pour gérer les exceptions de code managé avec élégance.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-107">Ideal for any tasks for which <xref:System.Windows.Forms.MessageBox> may be used, <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> is designed to elegantly handle managed code exceptions.</span></span> <span data-ttu-id="fc5ef-108">La boîte de message d'exception vous permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fc5ef-108">The exception message box allows you to do the following:</span></span>  
  
-   <span data-ttu-id="fc5ef-109">Fournir un texte de bouton personnalisé pour cinq boutons maximum.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-109">Provide customized button text for up to five buttons.</span></span> <span data-ttu-id="fc5ef-110">Les boutons et la boîte de dialogue sont redimensionnés automatiquement en fonction de la longueur du texte.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-110">Buttons and the dialog box resize automatically for different text lengths.</span></span>  
  
-   <span data-ttu-id="fc5ef-111">Permettre aux utilisateurs de copier facilement le titre du message, le texte du message, le texte du bouton et les liens d'aide (le cas échant) vers le Presse-papiers ou d'envoyer ces informations dans un message électronique.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-111">Allow users to easily copy the message title, text, button text, and help links (if any) to the Clipboard or send this information in an e-mail message.</span></span>  
  
-   <span data-ttu-id="fc5ef-112">Affichez toutes les exceptions et les erreurs sous-jacentes dans une arborescence de relations hiérarchiques lorsque les utilisateurs cliquent sur **des informations supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-112">Display all underlying exceptions and errors in a hierarchical relationship tree when users click **Additional Information**.</span></span>  
  
-   <span data-ttu-id="fc5ef-113">Permettre aux utilisateurs de décider s'il faut afficher le message lorsque la même exception se produit de nouveau.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-113">Allow users to decide whether to display the message when the same exception occurs again.</span></span>  
  
-   <span data-ttu-id="fc5ef-114">Accéder à un système d'aide en ligne en utilisant un lien d'aide associé à l'exception.</span><span class="sxs-lookup"><span data-stu-id="fc5ef-114">Access an online help system by using a help link associated with the exception.</span></span>  
  
 <span data-ttu-id="fc5ef-115">Pour plus d’informations, consultez [boîte de message d’exception de programme](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span><span class="sxs-lookup"><span data-stu-id="fc5ef-115">For more information, see [Program Exception Message Box](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span></span>  
  
  
