---
title: Éditeur de tâche FTP (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.general.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 28b46fdd-b04a-4f97-a99f-883f5735a6d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0cb4ffe2fa44e76890f6b70912f84dbcaa8f2cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602891"
---
# <a name="ftp-task-editor-general-page"></a><span data-ttu-id="cc0a1-102">Éditeur de tâche FTP (page Général)</span><span class="sxs-lookup"><span data-stu-id="cc0a1-102">FTP Task Editor (General Page)</span></span>
  <span data-ttu-id="cc0a1-103">La page **Général** de la boîte de dialogue **Éditeur de tâche FTP** permet de spécifier le gestionnaire de connexions FTP qui se connecte au serveur FTP avec lequel la tâche communique.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-103">Use the **General** page of the **FTP Task Editor** dialog box to specify the FTP connection manager that connects to the FTP server that the task communicates with.</span></span> <span data-ttu-id="cc0a1-104">Vous pouvez également nommer et décrire cette tâche FTP.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-104">You can also name and describe the FTP task.</span></span>  
  
 <span data-ttu-id="cc0a1-105">Pour en savoir plus sur cette tâche, consultez [Tâche FTP](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="cc0a1-105">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cc0a1-106">Options</span><span class="sxs-lookup"><span data-stu-id="cc0a1-106">Options</span></span>  
 <span data-ttu-id="cc0a1-107">**Connexion FTP**</span><span class="sxs-lookup"><span data-stu-id="cc0a1-107">**FtpConnection**</span></span>  
 <span data-ttu-id="cc0a1-108">Sélectionnez un gestionnaire de connexions FTP ou cliquez sur \<**New connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-108">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cc0a1-109">Le gestionnaire de connexions FTP prend en charge uniquement l'authentification anonyme et l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-109">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="cc0a1-110">Il ne prend pas en charge l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-110">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="cc0a1-111">**Rubriques connexes :** [Gestionnaires de connexions FTP](connection-manager/ftp-connection-manager.md), [Éditeur du gestionnaire de connexions FTP](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="cc0a1-111">**Related Topics**: [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="cc0a1-112">**Arrêt en cas d'échec de l'opération**</span><span class="sxs-lookup"><span data-stu-id="cc0a1-112">**StopOnFailure**</span></span>  
 <span data-ttu-id="cc0a1-113">Indique si la tâche FTP se termine en cas d'échec de l'opération.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-113">Indicate whether the FTP task terminates if an FTP operation fails.</span></span>  
  
 <span data-ttu-id="cc0a1-114">**Nom**</span><span class="sxs-lookup"><span data-stu-id="cc0a1-114">**Name**</span></span>  
 <span data-ttu-id="cc0a1-115">Fournit un nom unique pour la tâche FTP.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-115">Provide a unique name for the FTP task.</span></span> <span data-ttu-id="cc0a1-116">Ce nom sert d'étiquette à l'icône de la tâche.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc0a1-117">Les noms de tâche doivent être uniques dans un package.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="cc0a1-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="cc0a1-118">**Description**</span></span>  
 <span data-ttu-id="cc0a1-119">Tapez une description de la tâche FTP.</span><span class="sxs-lookup"><span data-stu-id="cc0a1-119">Type a description of the FTP task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0a1-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc0a1-120">See Also</span></span>  
 <span data-ttu-id="cc0a1-121">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cc0a1-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="cc0a1-122">[Éditeur de tâche FTP &#40;page transfert de fichiers&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span><span class="sxs-lookup"><span data-stu-id="cc0a1-122">[FTP Task Editor &#40;File Transfer Page&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span></span>  
 [<span data-ttu-id="cc0a1-123">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="cc0a1-123">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
