---
title: Gestionnaire de connexions SMTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMTP
- SMTP connection manager [Integration Services]
- connection managers [Integration Services], SMTP
ms.assetid: 3795d442-714b-4bbb-9acd-75bf277a468a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f3c090ab672790901baae01ae86f8d22e008b4ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708548"
---
# <a name="smtp-connection-manager"></a><span data-ttu-id="1a410-102">Gestionnaire de connexions SMTP</span><span class="sxs-lookup"><span data-stu-id="1a410-102">SMTP Connection Manager</span></span>
  <span data-ttu-id="1a410-103">Un gestionnaire de connexions SMTP permet à un package de se connecter à un serveur SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="1a410-103">An SMTP connection manager enables a package to connect to a Simple Mail Transfer Protocol (SMTP) server.</span></span> <span data-ttu-id="1a410-104">La tâche Envoyer un message incluse dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilise un gestionnaire de connexions SMTP.</span><span class="sxs-lookup"><span data-stu-id="1a410-104">The Send Mail task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an SMTP connection manager.</span></span>  
  
 <span data-ttu-id="1a410-105">Lorsque vous utilisez Microsoft Exchange comme serveur SMTP, vous pouvez être amené à configurer le gestionnaire de connexions SMTP de manière à utiliser l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="1a410-105">When using Microsoft Exchange as the SMTP server, you may need to configure the SMTP connection manager to use Windows Authentication.</span></span> <span data-ttu-id="1a410-106">Les serveurs Exchange peuvent être configurés pour ne pas autoriser les connexions SMTP non authentifiées.</span><span class="sxs-lookup"><span data-stu-id="1a410-106">Exchange servers may be configured to not allow unauthenticated SMTP connections.</span></span>  
  
## <a name="configuration-the-smtp-connection-manager"></a><span data-ttu-id="1a410-107">Configuration du gestionnaire de connexions SMTP</span><span class="sxs-lookup"><span data-stu-id="1a410-107">Configuration the SMTP Connection Manager</span></span>  
 <span data-ttu-id="1a410-108">Lorsque vous ajoutez un gestionnaire de connexions SMTP à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera converti en connexion SMTP au moment de l'exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la collection `Connections` du package.</span><span class="sxs-lookup"><span data-stu-id="1a410-108">When you add an SMTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="1a410-109">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `SMTP`.</span><span class="sxs-lookup"><span data-stu-id="1a410-109">The `ConnectionManagerType` property of the connection manager is set to `SMTP`.</span></span>  
  
 <span data-ttu-id="1a410-110">Vous pouvez configurer un gestionnaire de connexions SMTP de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="1a410-110">You can configure an SMTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="1a410-111">Spécifiez une chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="1a410-111">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="1a410-112">Indiquez le nom d'un serveur SMTP.</span><span class="sxs-lookup"><span data-stu-id="1a410-112">Specify the name of an SMTP server.</span></span>  
  
-   <span data-ttu-id="1a410-113">Spécifiez la méthode d'authentification à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1a410-113">Specify the authentication method to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1a410-114">Le gestionnaire de connexions SMTP prend en charge uniquement l'authentification anonyme et l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="1a410-114">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="1a410-115">Il ne prend pas en charge l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="1a410-115">It does not support basic authentication.</span></span>  
  
-   <span data-ttu-id="1a410-116">Permet d'indiquer si les communications doivent être chiffrées à l'aide de SSL (Secure Sockets Layer) lors de l'envoi de messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="1a410-116">Specify whether to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
 <span data-ttu-id="1a410-117">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="1a410-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="1a410-118">Pour plus d’informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Éditeur du gestionnaire de connexions SMTP](../smtp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="1a410-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMTP Connection Manager Editor](../smtp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="1a410-119">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="1a410-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
