---
title: Éditeur du gestionnaire de connexions SMTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.smtpconnection.f1
helpviewer_keywords:
- SMTP Connection Manager Editor
ms.assetid: 2693de0d-b04d-4325-a856-ce667d2b8aa1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14ed49f64b9faca40f575fc6760a8d25c0d4573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709708"
---
# <a name="smtp-connection-manager-editor"></a><span data-ttu-id="b76a0-102">Éditeur du gestionnaire de connexions SMTP</span><span class="sxs-lookup"><span data-stu-id="b76a0-102">SMTP Connection Manager Editor</span></span>
  <span data-ttu-id="b76a0-103">Utilisez la boîte de dialogue **Éditeur du gestionnaire de connexions SMTP** pour spécifier un serveur SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="b76a0-103">Use the **SMTP Connection Manager Editor** dialog box to specify a Simple Mail Transfer Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="b76a0-104">Pour en savoir plus sur le gestionnaire de connexions SMTP, consultez [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b76a0-104">To learn more about the SMTP connection manager, see [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b76a0-105">Options</span><span class="sxs-lookup"><span data-stu-id="b76a0-105">Options</span></span>  
 <span data-ttu-id="b76a0-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b76a0-106">**Name**</span></span>  
 <span data-ttu-id="b76a0-107">Donnez un nom unique au gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="b76a0-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="b76a0-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="b76a0-108">**Description**</span></span>  
 <span data-ttu-id="b76a0-109">Décrivez le gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="b76a0-109">Describe the connection manager.</span></span> <span data-ttu-id="b76a0-110">Il est recommandé d'indiquer ici l'usage auquel le gestionnaire de connexions est destiné, de sorte que les packages soient correctement documentés et plus faciles à gérer.</span><span class="sxs-lookup"><span data-stu-id="b76a0-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="b76a0-111">**Serveur SMTP**</span><span class="sxs-lookup"><span data-stu-id="b76a0-111">**SMTP server**</span></span>  
 <span data-ttu-id="b76a0-112">Indiquez le nom du serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="b76a0-112">Provide the name of the SMTP server.</span></span>  
  
 <span data-ttu-id="b76a0-113">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="b76a0-113">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="b76a0-114">Sélectionnez cette option pour envoyer des messages au moyen d'un serveur SMTP utilisant l'authentification Windows pour authentifier l'accès au serveur.</span><span class="sxs-lookup"><span data-stu-id="b76a0-114">Select to send mail using an SMTP server that uses Windows Authentication to authenticate access to the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b76a0-115">Le gestionnaire de connexions SMTP prend en charge uniquement l'authentification anonyme et l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="b76a0-115">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="b76a0-116">Il ne prend pas en charge l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="b76a0-116">It does not support basic authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b76a0-117">Lorsque vous utilisez Microsoft Exchange comme serveur SMTP, vous devrez peut-être définir **utiliser l’authentification Windows** sur `True` .</span><span class="sxs-lookup"><span data-stu-id="b76a0-117">When using Microsoft Exchange as the SMTP server, you may need to set **Use Windows Authentication** to `True`.</span></span> <span data-ttu-id="b76a0-118">Les serveurs Exchange peuvent être configurés de manière à interdire les connexions SMTP non authentifiées.</span><span class="sxs-lookup"><span data-stu-id="b76a0-118">Exchange servers may be configured to disallow unauthenticated SMTP connections.</span></span>  
  
 <span data-ttu-id="b76a0-119">**Activer SSL (Secure Sockets Layer)**</span><span class="sxs-lookup"><span data-stu-id="b76a0-119">**Enable Secure Sockets Layer (SSL)**</span></span>  
 <span data-ttu-id="b76a0-120">Sélectionnez cette option pour chiffrer la communication au moyen de Secure Sockets Layer (SSL) lors de l'envoi de messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="b76a0-120">Select to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76a0-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b76a0-121">See Also</span></span>  
 [<span data-ttu-id="b76a0-122">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="b76a0-122">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
