---
title: Débogage du code des extensions pour le traitement des données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- debugging data processing extensions [Reporting Services]
- troubleshooting [Reporting Services], data processing extensions
- data processing extensions [Reporting Services], debugging
ms.assetid: e963e205-9ae0-446d-97df-028a1d2727d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bf7490145f91ee8b3cfc2357c34010bed593ed9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604388"
---
# <a name="debugging-data-processing-extension-code"></a><span data-ttu-id="9cb89-102">Débogage du code des extensions pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="9cb89-102">Debugging Data Processing Extension Code</span></span>
  <span data-ttu-id="9cb89-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] fournit plusieurs outils de débogage qui peuvent vous aider à analyser le code de vos extensions pour le traitement des données et à localiser les erreurs qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="9cb89-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your data processing extension code and locate errors in it.</span></span> <span data-ttu-id="9cb89-104">L'outil le plus approprié dépend de ce que vous essayez d'accomplir.</span><span class="sxs-lookup"><span data-stu-id="9cb89-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="9cb89-105">Cet exemple utilise [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cb89-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-data-processing-extension-code"></a><span data-ttu-id="9cb89-106">Pour déboguer le code de votre extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="9cb89-106">To debug your data processing extension code</span></span>  
  
1.  <span data-ttu-id="9cb89-107">Lancez [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] et ouvrez votre projet d'extension pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="9cb89-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)], and open your data processing extension project.</span></span>  
  
2.  <span data-ttu-id="9cb89-108">Générez le projet et déployez votre assembly d'extension pour le traitement des données ainsi que le fichier .pdb associé sur le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="9cb89-108">Build the project, and deploy your data processing extension assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="9cb89-109">Pour plus d’informations sur le déploiement, consultez [Procédure : déployer une extension pour le traitement des données sur le Concepteur de rapports](deploying-a-data-processing-extension-to-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="9cb89-109">For more information about deployment, see [How to: Deploy a Data Processing Extension to Report Designer](deploying-a-data-processing-extension-to-report-designer.md).</span></span>  
  
3.  <span data-ttu-id="9cb89-110">Ouvrez un nouveau projet de rapport dans [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] tout en laissant ouvert le code de votre extension pour le traitement des données dans une fenêtre distincte de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cb89-110">Open a new Report Project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] while leaving your data processing extension code open in a separate window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="9cb89-111">Accédez à la fenêtre de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] qui contient votre projet d'extension pour le traitement des données et définissez des points d'arrêt dans votre code.</span><span class="sxs-lookup"><span data-stu-id="9cb89-111">Navigate to the window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that contains your data processing extension project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="9cb89-112">La fenêtre du projet d’extension pour le traitement des données étant toujours active, cliquez sur **Attacher au processus** dans le menu **Déboguer**.</span><span class="sxs-lookup"><span data-stu-id="9cb89-112">With the data processing extension project window still active, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="9cb89-113">La boîte de dialogue **Attacher au processus** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="9cb89-113">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="9cb89-114">Dans la liste des processus, sélectionnez le processus devenv.exe qui correspond à votre projet de rapport, puis cliquez sur **Attacher**.</span><span class="sxs-lookup"><span data-stu-id="9cb89-114">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="9cb89-115">Définissez votre source de données de rapport à l’aide de l’onglet **Données du rapport** du projet de rapport.</span><span class="sxs-lookup"><span data-stu-id="9cb89-115">Define your report data source using the **Report Data** tab of the Report Project.</span></span> <span data-ttu-id="9cb89-116">Vous utiliserez très probablement le Concepteur de requêtes générique pour exécuter une requête sur votre source de données personnalisée.</span><span class="sxs-lookup"><span data-stu-id="9cb89-116">You will most likely use the generic Query Designer to execute a query against your custom data source.</span></span> <span data-ttu-id="9cb89-117">Celle-ci doit appeler le débogueur et exécuter le code correspondant à vos points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="9cb89-117">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="9cb89-118">Exécutez le code pas à pas à l'aide de la touche F11.</span><span class="sxs-lookup"><span data-stu-id="9cb89-118">Step through your code using the F11 key.</span></span> <span data-ttu-id="9cb89-119">Pour plus d'informations sur l'utilisation de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pour le débogage, consultez votre documentation [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9cb89-119">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb89-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9cb89-120">See Also</span></span>  
 <span data-ttu-id="9cb89-121">[Déploiement d’une extension pour le traitement des données](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="9cb89-121">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="9cb89-122">[Extensions Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="9cb89-122">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="9cb89-123">[Implémentation d’une extension pour le traitement des données](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="9cb89-123">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="9cb89-124">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9cb89-124">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
