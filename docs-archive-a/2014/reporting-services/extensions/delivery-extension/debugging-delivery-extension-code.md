---
title: Débogage du code d’extension de remise | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], debugging
- debugging delivery extensions [Reporting Services]
- troubleshooting [Reporting Services], delivery extensions
ms.assetid: a7d959da-5005-4a50-aca7-2cef36aa9947
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb80ac97f5c0e346b208784f1fa5b857ff93ef57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708923"
---
# <a name="debugging-delivery-extension-code"></a><span data-ttu-id="b5b35-102">Débogage du code d'extension de remise</span><span class="sxs-lookup"><span data-stu-id="b5b35-102">Debugging Delivery Extension Code</span></span>
  <span data-ttu-id="b5b35-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] fournit plusieurs outils de débogage qui peuvent vous aider à analyser le code de vos extensions de remise et à localiser les erreurs qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="b5b35-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your delivery extension code and locate errors in it.</span></span> <span data-ttu-id="b5b35-104">L'outil le plus approprié dépend de ce que vous essayez d'accomplir.</span><span class="sxs-lookup"><span data-stu-id="b5b35-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="b5b35-105">Cet exemple utilise [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5b35-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-delivery-extension-code"></a><span data-ttu-id="b5b35-106">Pour déboguer votre code d'extension de remise</span><span class="sxs-lookup"><span data-stu-id="b5b35-106">To debug your delivery extension code</span></span>  
  
1.  <span data-ttu-id="b5b35-107">Lancez [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] et ouvrez votre projet d’extension de remise.</span><span class="sxs-lookup"><span data-stu-id="b5b35-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] and open your delivery extension project.</span></span>  
  
2.  <span data-ttu-id="b5b35-108">Générez le projet et déployez votre assembly d'extension de remise ainsi que le fichier .pdb associé sur le serveur de rapports et le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b5b35-108">Build the project and deploy your delivery extension assembly and the accompanying .pdb file to the report server and Report Manager.</span></span> <span data-ttu-id="b5b35-109">Pour plus d’informations sur le déploiement, consultez [Déploiement d’une extension de remise](deploying-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="b5b35-109">For more information about deployment, see [Deploying a Delivery Extension](deploying-a-delivery-extension.md).</span></span>  
  
3.  <span data-ttu-id="b5b35-110">Si vous avez écrit une interface utilisateur d'abonnement pour étendre le Gestionnaire de rapports, ouvrez Internet Explorer et naviguez jusqu'au Gestionnaire de rapports en laissant votre code d'extension de remise ouvert dans [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5b35-110">If you have written a subscription user interface to extend Report Manager, open Internet Explorer and navigate to Report Manager while leaving your delivery extension code open in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="b5b35-111">Si vous n'avez pas d'interface utilisateur d'abonnement déployée pour le Gestionnaire de rapports, ouvrez simplement l'application cliente dans laquelle vous appelez votre extension de remise à l'aide de l'API SOAP.</span><span class="sxs-lookup"><span data-stu-id="b5b35-111">If you do not have a subscription user interface deployed for Report Manager, simply open the client application from which you call your delivery extension using the SOAP API.</span></span>  
  
4.  <span data-ttu-id="b5b35-112">Naviguez jusqu'à [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] et votre projet d'extension de remise et définissez des points d'arrêt dans votre code.</span><span class="sxs-lookup"><span data-stu-id="b5b35-112">Navigate to [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] and your delivery extension project, and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="b5b35-113">Le projet d’extension de remise demeurant dans la fenêtre active, cliquez sur **Attacher au processus** dans le menu **Déboguer**.</span><span class="sxs-lookup"><span data-stu-id="b5b35-113">With the delivery extension project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="b5b35-114">La boîte de dialogue **Attacher au processus** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="b5b35-114">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="b5b35-115">Dans la liste de processus, sélectionnez aspnet_wp.exe (ou w3wp.exe, si votre application est déployée sur IIS 6.0) et cliquez sur **Attacher**.</span><span class="sxs-lookup"><span data-stu-id="b5b35-115">From the list of processes, select the aspnet_wp.exe process (or w3wp.exe if your application is deployed on IIS 6.0), and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="b5b35-116">Définissez un nouvel abonnement à l'aide de votre extension de remise.</span><span class="sxs-lookup"><span data-stu-id="b5b35-116">Define a new subscription using your delivery extension.</span></span> <span data-ttu-id="b5b35-117">Vous utiliserez très probablement le Gestionnaire de rapports ou l'API SOAP.</span><span class="sxs-lookup"><span data-stu-id="b5b35-117">You will most likely use Report Manager or the SOAP API.</span></span> <span data-ttu-id="b5b35-118">Celle-ci doit appeler le débogueur et exécuter le code correspondant à vos points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="b5b35-118">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="b5b35-119">Exécutez le code pas à pas à l’aide de la touche **F11**.</span><span class="sxs-lookup"><span data-stu-id="b5b35-119">Step through your code using the **F11** key.</span></span> <span data-ttu-id="b5b35-120">Pour plus d'informations sur l'utilisation de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pour le débogage, consultez votre documentation [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5b35-120">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b35-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5b35-121">See Also</span></span>  
 <span data-ttu-id="b5b35-122">[Implémentation d’une extension de remise](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="b5b35-122">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="b5b35-123">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b5b35-123">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
