---
title: Éditeur du gestionnaire de connexions WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmiconnection.f1
helpviewer_keywords:
- WMI Connection Manager Editor
ms.assetid: 0ef2c913-0779-4a07-989e-3361cd83170b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e85cdd2157c8ebe4cb9e6b53f8c3b47ff102a7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613508"
---
# <a name="wmi-connection-manager-editor"></a><span data-ttu-id="89129-102">Éditeur du gestionnaire de connexions WMI</span><span class="sxs-lookup"><span data-stu-id="89129-102">WMI Connection Manager Editor</span></span>
  <span data-ttu-id="89129-103">Utilisez la boîte de dialogue **Gestionnaire de connexions WMI** pour spécifier une connexion Microsoft Windows Management Instrumentation (WMI) à un serveur.</span><span class="sxs-lookup"><span data-stu-id="89129-103">Use the **WMI Connection Manager** dialog box to specify a Microsoft Windows Management Instrumentation (WMI) connection to a server.</span></span>  
  
 <span data-ttu-id="89129-104">Pour en savoir plus sur le gestionnaire de connexions WMI, consultez [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="89129-104">To learn more about the WMI connection manager, see [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="89129-105">Options</span><span class="sxs-lookup"><span data-stu-id="89129-105">Options</span></span>  
 <span data-ttu-id="89129-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="89129-106">**Name**</span></span>  
 <span data-ttu-id="89129-107">Donnez un nom unique au gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="89129-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="89129-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="89129-108">**Description**</span></span>  
 <span data-ttu-id="89129-109">Décrivez le gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="89129-109">Describe the connection manager.</span></span> <span data-ttu-id="89129-110">Il est recommandé d'indiquer ici l'usage auquel le gestionnaire de connexions est destiné, de sorte que les packages soient correctement documentés et plus faciles à gérer.</span><span class="sxs-lookup"><span data-stu-id="89129-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="89129-111">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="89129-111">**Server name**</span></span>  
 <span data-ttu-id="89129-112">Fournissez le nom du serveur pour lequel vous souhaitez établir la connexion WMI.</span><span class="sxs-lookup"><span data-stu-id="89129-112">Provide the name of the server to which you want to make the WMI connection.</span></span>  
  
 <span data-ttu-id="89129-113">**Espace de noms**</span><span class="sxs-lookup"><span data-stu-id="89129-113">**Namespace**</span></span>  
 <span data-ttu-id="89129-114">Spécifiez l'espace de noms WMI.</span><span class="sxs-lookup"><span data-stu-id="89129-114">Specify the WMI namespace.</span></span>  
  
 <span data-ttu-id="89129-115">**Utiliser l’authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="89129-115">**Use Windows authentication**</span></span>  
 <span data-ttu-id="89129-116">Sélectionnez cette option pour utiliser l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="89129-116">Select to use Windows Authentication.</span></span> <span data-ttu-id="89129-117">Si vous utilisez l'authentification Windows, vous n'avez pas besoin de fournir un nom d'utilisateur ou un mot de passe pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="89129-117">If you use Windows Authentication, you do not need to provide a user name or password for the connection.</span></span>  
  
 <span data-ttu-id="89129-118">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="89129-118">**User name**</span></span>  
 <span data-ttu-id="89129-119">Si vous n'utilisez pas l'authentification Windows, vous devez fournir un nom d'utilisateur pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="89129-119">If you do not use Windows Authentication, you must provide a user name for the connection.</span></span>  
  
 <span data-ttu-id="89129-120">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="89129-120">**Password**</span></span>  
 <span data-ttu-id="89129-121">Si vous n'utilisez pas l'authentification Windows, vous devez fournir le mot de passe de la connexion.</span><span class="sxs-lookup"><span data-stu-id="89129-121">If you do not use Windows Authentication, you must provide the password for the connection.</span></span>  
  
 <span data-ttu-id="89129-122">**Test**</span><span class="sxs-lookup"><span data-stu-id="89129-122">**Test**</span></span>  
 <span data-ttu-id="89129-123">Testez les paramètres du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="89129-123">Test the connection manager settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89129-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89129-124">See Also</span></span>  
 <span data-ttu-id="89129-125">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="89129-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="89129-126">[Fournisseur WMI pour les concepts de gestion de configuration](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="89129-126">[WMI Provider for Configuration Management Concepts](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="89129-127">Fournisseur WMI pour les concepts des événements de serveur</span><span class="sxs-lookup"><span data-stu-id="89129-127">WMI Provider for Server Events Concepts</span></span>](../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md)  
  
  
