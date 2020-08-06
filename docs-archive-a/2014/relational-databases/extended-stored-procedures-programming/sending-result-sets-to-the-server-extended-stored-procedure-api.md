---
title: Envoi de jeux de résultats au serveur (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], sending result sets
- result sets [SQL Server], extended stored procedures
ms.assetid: 9d54673d-ea9d-4ac6-825a-f216ad8b0e34
author: rothja
ms.author: jroth
ms.openlocfilehash: 82984440f96416189eb18f900764ee7bdaf05a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600022"
---
# <a name="sending-result-sets-to-the-server-extended-stored-procedure-api"></a><span data-ttu-id="de2fa-102">Envoi de jeux de résultats au serveur (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="de2fa-102">Sending Result Sets to the Server (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="de2fa-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="de2fa-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="de2fa-104">Lors de l’envoi d’un jeu de résultats à [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la procédure stockée étendue doit appeler l’API appropriée comme suit :</span><span class="sxs-lookup"><span data-stu-id="de2fa-104">When sending a result set to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the extended stored procedure should call the appropriate API as follows:</span></span>  
  
-   <span data-ttu-id="de2fa-105">La fonction **srv_sendmsg** peut être appelée dans n’importe quel ordre avant ou après que toutes les lignes (le cas échéant) ont été envoyées avec **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="de2fa-105">The **srv_sendmsg** function may be called in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="de2fa-106">Tous les messages doivent être envoyés au client avant que l’état d’achèvement ne soit envoyé avec **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="de2fa-106">All messages must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="de2fa-107">La fonction **srv_sendrow** est appelée une fois pour chaque ligne envoyée au client.</span><span class="sxs-lookup"><span data-stu-id="de2fa-107">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="de2fa-108">Toutes les lignes doivent être envoyées au client avant que les messages, valeurs d’État ou États d’achèvement ne soient envoyés avec **srv_sendmsg**, l’argument **srv_status** de **SRV_PFIELD**ou **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="de2fa-108">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, the **srv_status** argument of **srv_pfield**, or **srv_senddone**.</span></span>  
  
-   <span data-ttu-id="de2fa-109">L’envoi d’une ligne dont toutes les colonnes n’ont pas été définies avec **srv_describe** amène l’application à déclencher un message d’erreur d’information et à retourner Fail au client.</span><span class="sxs-lookup"><span data-stu-id="de2fa-109">Sending a row that has not had all its columns defined with **srv_describe** causes the application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="de2fa-110">Dans ce cas, la ligne n'est pas envoyée.</span><span class="sxs-lookup"><span data-stu-id="de2fa-110">In this case, the row is not sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de2fa-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de2fa-111">See Also</span></span>  
 [<span data-ttu-id="de2fa-112">Création de procédures stockées étendues</span><span class="sxs-lookup"><span data-stu-id="de2fa-112">Creating Extended Stored Procedures</span></span>](creating-extended-stored-procedures.md)  
  
  
