---
title: Développement d’une interface utilisateur pour un module fournisseur d’informations personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom user interface [Integration Services], custom log providers
- custom log providers [Integration Services], developing custom user interface
ms.assetid: 6fd2d269-d87a-4134-82a1-40a09b3b5453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c3ce6cf5ad744e307bbb049347047bf94fc5a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601616"
---
# <a name="developing-a-user-interface-for-a-custom-log-provider"></a><span data-ttu-id="5f82b-102">Développement d'une interface utilisateur pour un module fournisseur d'informations personnalisé</span><span class="sxs-lookup"><span data-stu-id="5f82b-102">Developing a User Interface for a Custom Log Provider</span></span>
  <span data-ttu-id="5f82b-103">De nombreux modules fournisseurs d’informations [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] ont une interface utilisateur personnalisée qui implémente <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> et remplace la zone de texte **Configuration** dans la boîte de dialogue **Configurer les journaux SSIS** par la liste déroulante filtrée des gestionnaires de connexions disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f82b-103">Many [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] log providers have a custom user interface that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> and replaces the **Configuration** text box in the **Configure SSIS Logs** dialog box with a filtered dropdown list of available connection managers.</span></span> <span data-ttu-id="5f82b-104">Toutefois, les interfaces utilisateur personnalisées des modules fournisseurs d'informations personnalisés ne sont pas implémentées dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f82b-104">However, custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
<span data-ttu-id="5f82b-105">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5f82b-105">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5f82b-106">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="5f82b-106">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5f82b-107">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="5f82b-107">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5f82b-108">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="5f82b-108">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f82b-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f82b-109">See Also</span></span>  
 <span data-ttu-id="5f82b-110">[Création d’un module fournisseur d’informations personnalisé](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="5f82b-110">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="5f82b-111">Codage d'un module fournisseur d'informations personnalisé</span><span class="sxs-lookup"><span data-stu-id="5f82b-111">Coding a Custom Log Provider</span></span>](coding-a-custom-log-provider.md)  
  
  
