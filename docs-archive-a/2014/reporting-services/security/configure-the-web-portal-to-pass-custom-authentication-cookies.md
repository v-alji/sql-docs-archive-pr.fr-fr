---
title: Configurer Gestionnaire de rapports pour passer des cookies d’authentification personnalisée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: 91aeb053-149e-4562-ae4c-a688d0e1b2ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 90e8798fb91152ec64e7f290dc1522fc8eaa451c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602712"
---
# <a name="configure-report-manager-to-pass-custom-authentication-cookies"></a><span data-ttu-id="13974-102">Configurer le Gestionnaire de rapports pour passer des cookies d'authentification personnalisée</span><span class="sxs-lookup"><span data-stu-id="13974-102">Configure Report Manager to Pass Custom Authentication Cookies</span></span>
  <span data-ttu-id="13974-103">Si vous utilisez une extension d'authentification personnalisée, vous devez configurer le Gestionnaire de rapports pour transmettre des cookies d'authentification personnalisée.</span><span class="sxs-lookup"><span data-stu-id="13974-103">If you are using a custom authentication extension, you should configure Report Manager to transmit custom authentication cookies.</span></span> <span data-ttu-id="13974-104">Sinon, le Gestionnaire de rapports transmet uniquement des cookies via des demandes HTTP spécifiques au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="13974-104">Otherwise, Report Manager will only transmit cookies through HTTP requests specific to the report server.</span></span> <span data-ttu-id="13974-105">Si vous souhaitez transmettre des cookies supplémentaires, vous devez modifier le fichier RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="13974-105">If you want to transmit additional cookies, you must modify the RSReportServer.Config file.</span></span>  
  
## <a name="modifying-the-rsreportserverconfig-file"></a><span data-ttu-id="13974-106">Modification du fichier RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="13974-106">Modifying the RSReportServer.Config File</span></span>  
 <span data-ttu-id="13974-107">Vous pouvez activer Gestionnaire de rapports pour transmettre des cookies supplémentaires via le serveur de rapports en ajoutant un `PassThroughCookies` élément <> aux paramètres de configuration Gestionnaire de rapports dans le fichier RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="13974-107">You can enable Report Manager to transmit additional cookies through to the report server by adding a <`PassThroughCookies`> element to the Report Manager configuration settings in the RSReportServer.config file.</span></span> <span data-ttu-id="13974-108">La transmission de cookies supplémentaires est utile dans une solution d'authentification unique qui requiert non seulement les cookies d'authentification du serveur de rapports mais également les cookies d'un système d'authentification tiers.</span><span class="sxs-lookup"><span data-stu-id="13974-108">Transmitting additional cookies is helpful in a single sign-on authentication solution that requires not only the report server authentication cookies, but also cookies from a third-party authentication system.</span></span>  
  
 <span data-ttu-id="13974-109">Pour activer la transmission de cookies supplémentaires via des requêtes HTTP lorsque vous utilisez le Gestionnaire de rapports, définissez les éléments ci-après dans le fichier RSReportServer.config :</span><span class="sxs-lookup"><span data-stu-id="13974-109">To enable additional cookies to be transmitted through HTTP requests when using Report Manager, set the following elements in the RSReportServer.config file:</span></span>  
  
```  
<UI>  
   <CustomAuthenticationUI>  
      ...  
      <PassThroughCookies>  
         <PassThroughCookie>cookiename1</PassThroughCookie>  
         <PassThroughCookie>cookiename2</PassThroughCookie>  
      </PassThroughCookies>  
   </CustomAuthenticationUI>  
      ...  
</UI>  
```  
  
## <a name="see-also"></a><span data-ttu-id="13974-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13974-110">See Also</span></span>  
 <span data-ttu-id="13974-111">[Authentification avec le serveur de rapports](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="13974-111">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="13974-112">[Fichier de configuration RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="13974-112">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="13974-113">[Présentation des extensions de sécurité](../extensions/security-extension/security-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="13974-113">[Security Extensions Overview](../extensions/security-extension/security-extensions-overview.md) </span></span>  
 [<span data-ttu-id="13974-114">Configurer et administrer un serveur de rapports &#40;SSRS en mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="13974-114">Configure and Administer a Report Server &#40;SSRS Native Mode&#41;</span></span>](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md)  
  
  
