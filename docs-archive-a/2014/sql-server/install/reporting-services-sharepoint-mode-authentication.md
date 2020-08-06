---
title: Reporting Services l’authentification en mode SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade SharePoint Mode [Reporting Services]
- SharePoint integration
- SharePoint Mode
ms.assetid: 2c19794a-dd55-4fe5-b901-6dd93e9f6beb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3b1316a1a49726ab0754f39160125425fec116d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705932"
---
# <a name="reporting-services-sharepoint-mode-authentication"></a><span data-ttu-id="c508d-102">Authentification en mode SharePoint de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c508d-102">Reporting Services SharePoint Mode Authentication</span></span>
  <span data-ttu-id="c508d-103">Utilisez la page **Authentification en mode SharePoint de Reporting Services** de l'Assistant Installation de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour spécifier les informations d'identification du compte de service utilisé dans l'installation actuelle de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c508d-103">Use the **Reporting Services SharePoint Mode Authentication** page of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the credentials of the service account that is used in the current [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="c508d-104">Les informations d'identification seront utilisées pour créer un pool d'applications SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c508d-104">The credentials will be used to create a new SharePoint application pool.</span></span> <span data-ttu-id="c508d-105">Une application de service SharePoint [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sera également créée.</span><span class="sxs-lookup"><span data-stu-id="c508d-105">Also, one new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint service application will be created.</span></span> <span data-ttu-id="c508d-106">Le nom de l'application de service contiendra le nom de l'instance précédente de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c508d-106">The service application name will contain the name of the previous [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c508d-107">Options</span><span class="sxs-lookup"><span data-stu-id="c508d-107">Options</span></span>  
  
-   <span data-ttu-id="c508d-108">L'option **Nom de compte de pool d'applications SSRS :** est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="c508d-108">The **SSRS Application Pool Account Name:** option is read only.</span></span> <span data-ttu-id="c508d-109">La valeur est automatiquement remplie avec la valeur actuelle de l'installation existante [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que vous mettez à niveau.</span><span class="sxs-lookup"><span data-stu-id="c508d-109">The value is automatically populated with the current value from the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that you are upgrading.</span></span>  
  
-   <span data-ttu-id="c508d-110">L'option **Mot de passe du compte du pool d'applications SSRS :** sera désactivée si le compte de pool d'applications ne nécessite pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c508d-110">The **SSRS Application Pool Account Password:** option will be disabled if the application pool account does not require a password.</span></span> <span data-ttu-id="c508d-111">Par exemple, « NT Authority\NetworkService ».</span><span class="sxs-lookup"><span data-stu-id="c508d-111">For example, "NT Authority\NetworkService".</span></span> <span data-ttu-id="c508d-112">Si le compte de pool d'applications nécessite un mot de passe, vous ne pouvez pas poursuivre la mise à niveau tant que vous ne tapez pas le mot de passe correct.</span><span class="sxs-lookup"><span data-stu-id="c508d-112">If the application pool account does require a password, you cannot continue with upgrade until you type the correct password.</span></span>  
  
 <span data-ttu-id="c508d-113">Pour plus d’informations, consultez [mettre à niveau et migrer des Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) ( https://go.microsoft.com/fwlink/?LinkID=245628) .</span><span class="sxs-lookup"><span data-stu-id="c508d-113">For more information, see [Upgrade and Migrate Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) (https://go.microsoft.com/fwlink/?LinkID=245628).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c508d-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c508d-114">See Also</span></span>  
 [<span data-ttu-id="c508d-115">Mettre à niveau et migrer Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c508d-115">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkID=245628)  
  
  
