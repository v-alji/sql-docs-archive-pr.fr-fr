---
title: Propriétés du réseau | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LingerTimeout property
- EnableNagleAlgorithm property
- MinPendingAcceptExCount property
- MaxPendingSendCount property
- EnableBinaryXML property
- MinPendingReceiveCount property
- MaxCompletedReceiveCount property
- DisableNonblockingMode property
- RequestSizeThreshold property
- CompressionLevel property
- ReceiveBufferSize property
- EnableCompression property
- ServerSendTimeout property
- IPV4Support property
- MaxPendingReceiveCount property
- MaxPendingAcceptExCount property
- IPV6Support property
- MaxAllowedRequestSize property
- ServerReceiveTimeout property
- EnableLingerOnClose property
- InitialConnectTimeout property
- SendBufferSize property
- ScatterReceiveMultiplier property
- network properties [Analysis Services]
ms.assetid: ef4251e2-abe5-4c5b-9868-7549782d0244
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10ad5bbbcffdfc3d3c4fefe3111e4c4425919915
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604758"
---
# <a name="network-properties"></a><span data-ttu-id="3bfb1-102">Propriétés réseau</span><span class="sxs-lookup"><span data-stu-id="3bfb1-102">Network Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="3bfb1-103">prend en charge les propriétés de serveur répertoriées dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="3bfb1-104">Pour plus d'informations sur les autres propriétés de serveur et la façon de les configurer, consultez [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="3bfb1-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="3bfb1-105">**S'applique à :** mode serveur multidimensionnel et tabulaire</span><span class="sxs-lookup"><span data-stu-id="3bfb1-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="general"></a><span data-ttu-id="3bfb1-106">Général</span><span class="sxs-lookup"><span data-stu-id="3bfb1-106">General</span></span>  
 `ListenOnlyOnLocalConnections`  
 <span data-ttu-id="3bfb1-107">Propriété booléenne qui spécifie si l'écoute doit avoir lieu uniquement sur les connexions locales, par exemple localhost.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-107">A Boolean property that identifies whether to listen only on local connections, for example localhost.</span></span>  
  
## <a name="listener"></a><span data-ttu-id="3bfb1-108">Écouteur</span><span class="sxs-lookup"><span data-stu-id="3bfb1-108">Listener</span></span>  
 `IPV4Support`  
 <span data-ttu-id="3bfb1-109">Propriété dont la valeur est un entier 32 bits signé qui définit la prise en charge du protocole IPv4.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-109">A signed 32-bit integer property that defines support for IPv4 protocol.</span></span> <span data-ttu-id="3bfb1-110">Cette propriété peut prendre l'une des valeurs répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="3bfb1-110">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="3bfb1-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="3bfb1-111">Value</span></span>|<span data-ttu-id="3bfb1-112">Description</span><span class="sxs-lookup"><span data-stu-id="3bfb1-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3bfb1-113">*0*</span><span class="sxs-lookup"><span data-stu-id="3bfb1-113">*0*</span></span>|<span data-ttu-id="3bfb1-114">IPv4 est désactivé ; les clients ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-114">IPv4 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="3bfb1-115">*1*</span><span class="sxs-lookup"><span data-stu-id="3bfb1-115">*1*</span></span>|<span data-ttu-id="3bfb1-116">(Valeur par défaut) IPv4 est requis ; le serveur ne démarrera pas s'il ne peut pas écouter IPv4.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-116">(Default) IPv4 is required; server won't start if it cannot listen to IPv4.</span></span>|  
|<span data-ttu-id="3bfb1-117">*2*</span><span class="sxs-lookup"><span data-stu-id="3bfb1-117">*2*</span></span>|<span data-ttu-id="3bfb1-118">IPv4 est facultatif ; le serveur essaie d'écouter IPv4 mais démarre même s'il n'y parvient pas.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-118">IPv4 is optional; server tries to listen to IPv4 but starts even if unable to.</span></span>|  
  
 `IPV6Support`  
 <span data-ttu-id="3bfb1-119">Propriété dont la valeur est un entier 32 bits signé qui définit la prise en charge du protocole IPv6.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-119">A signed 32-bit integer property that defines support for IPv6 protocol.</span></span> <span data-ttu-id="3bfb1-120">Cette propriété peut prendre l'une des valeurs répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="3bfb1-120">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="3bfb1-121">Valeur</span><span class="sxs-lookup"><span data-stu-id="3bfb1-121">Value</span></span>|<span data-ttu-id="3bfb1-122">Description</span><span class="sxs-lookup"><span data-stu-id="3bfb1-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3bfb1-123">*0*</span><span class="sxs-lookup"><span data-stu-id="3bfb1-123">*0*</span></span>|<span data-ttu-id="3bfb1-124">IPv6 est désactivé ; les clients ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-124">IPv6 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="3bfb1-125">*1*</span><span class="sxs-lookup"><span data-stu-id="3bfb1-125">*1*</span></span>|<span data-ttu-id="3bfb1-126">(Valeur par défaut) IPv6 est requis ; le serveur ne démarrera pas s'il ne peut pas écouter IPv6.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-126">(Default) IPv6 is required; server won't start if it cannot listen to IPv6.</span></span>|  
|<span data-ttu-id="3bfb1-127">*2*</span><span class="sxs-lookup"><span data-stu-id="3bfb1-127">*2*</span></span>|<span data-ttu-id="3bfb1-128">IPv6 est facultatif ; le serveur essaie d'écouter IPv6 mais démarre même s'il n'y parvient pas.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-128">IPv6 is optional; server tries to listen to IPv6 but starts even if unable to.</span></span>|  
  
 `MaxAllowedRequestSize`  
 <span data-ttu-id="3bfb1-129">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-129">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RequestSizeThreshold`  
 <span data-ttu-id="3bfb1-130">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-130">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerReceiveTimeout`  
 <span data-ttu-id="3bfb1-131">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-131">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerSendTimeout`  
 <span data-ttu-id="3bfb1-132">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-132">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="requests"></a><span data-ttu-id="3bfb1-133">Demandes</span><span class="sxs-lookup"><span data-stu-id="3bfb1-133">Requests</span></span>  
 `EnableBinaryXML`  
 <span data-ttu-id="3bfb1-134">Propriété booléenne qui spécifie si le serveur prend en charge les demandes au format XML binaire.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-134">A Boolean property that specifies whether the server will recognize requests binary xml format.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="3bfb1-135">Propriété booléenne qui spécifie si la compression est activée pour les demandes.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-135">A Boolean property that specifies whether compression is enabled for requests.</span></span>  
  
## <a name="responses"></a><span data-ttu-id="3bfb1-136">Réponses</span><span class="sxs-lookup"><span data-stu-id="3bfb1-136">Responses</span></span>  
 `CompressionLevel`  
 <span data-ttu-id="3bfb1-137">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-137">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `EnableBinaryXML`  
 <span data-ttu-id="3bfb1-138">Propriété booléenne qui spécifie si le serveur prend en charge les réponses au format XML binaire.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-138">A Boolean property that specifies whether the server is enabled for binary xml responses.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="3bfb1-139">Propriété booléenne qui spécifie si la compression est activée pour les réponses aux demandes des clients.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-139">A Boolean property that specifies whether compression is enabled for responses to client requests.</span></span>  
  
## <a name="tcp"></a><span data-ttu-id="3bfb1-140">TCP</span><span class="sxs-lookup"><span data-stu-id="3bfb1-140">TCP</span></span>  
 `InitialConnectTimeout`  
 <span data-ttu-id="3bfb1-141">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxCompletedReceiveCount`  
 <span data-ttu-id="3bfb1-142">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingAcceptExCount`  
 <span data-ttu-id="3bfb1-143">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-143">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingReceiveCount`  
 <span data-ttu-id="3bfb1-144">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingSendCount`  
 <span data-ttu-id="3bfb1-145">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-145">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingAcceptExCount`  
 <span data-ttu-id="3bfb1-146">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingReceiveCount`  
 <span data-ttu-id="3bfb1-147">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ScatterReceiveMultiplier`  
 <span data-ttu-id="3bfb1-148">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ DisableNonblockingMode`  
 <span data-ttu-id="3bfb1-149">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ EnableLingerOnClose`  
 <span data-ttu-id="3bfb1-150">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\EnableNagleAlgorithm`  
 <span data-ttu-id="3bfb1-151">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ LingerTimeout`  
 <span data-ttu-id="3bfb1-152">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ ReceiveBufferSize`  
 <span data-ttu-id="3bfb1-153">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-153">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ SendBufferSize`  
 <span data-ttu-id="3bfb1-154">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bfb1-154">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bfb1-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3bfb1-155">See Also</span></span>  
 <span data-ttu-id="3bfb1-156">[Configurer les propriétés du serveur dans Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="3bfb1-156">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="3bfb1-157">Déterminer le mode serveur d'une instance Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3bfb1-157">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
