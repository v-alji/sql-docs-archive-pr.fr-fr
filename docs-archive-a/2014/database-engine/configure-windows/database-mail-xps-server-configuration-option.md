---
title: Database Mail XPs (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Database Mail XPs option
- Database Mail [SQL Server], enabling
ms.assetid: e22c4e63-1792-473b-af11-14a7931ca9ed
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 33ee15e862e0992f39373ec30275040c4fcacc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611274"
---
# <a name="database-mail-xps-server-configuration-option"></a><span data-ttu-id="dcbb0-102">Database Mail XPs (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="dcbb0-102">Database Mail XPs Server Configuration Option</span></span>
  <span data-ttu-id="dcbb0-103">Utilisez **l’option** pour activer la messagerie de base de données sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="dcbb0-103">Use the **DatabaseMail XPs** option to enable Database Mail on this server.</span></span> <span data-ttu-id="dcbb0-104">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="dcbb0-104">The possible values are:</span></span>  
  
-   <span data-ttu-id="dcbb0-105">**0** indique que la messagerie de base de données n’est pas disponible (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="dcbb0-105">**0** indicating Database Mail is not available (default).</span></span>  
  
-   <span data-ttu-id="dcbb0-106">**1** indique que la messagerie de base de données est disponible.</span><span class="sxs-lookup"><span data-stu-id="dcbb0-106">**1** indicating Database Mail is available.</span></span>  
  
 <span data-ttu-id="dcbb0-107">Le paramètre prend effet immédiatement, sans arrêt et redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="dcbb0-107">The setting takes effect immediately without a server stop and restart.</span></span>  
  
 <span data-ttu-id="dcbb0-108">Après avoir activé la messagerie de base de données, vous devez configurer une base de données hôte afin qu'elle utilise la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="dcbb0-108">After enabling Database Mail, you must configure a Database Mail host database to use Database Mail.</span></span>  
  
 <span data-ttu-id="dcbb0-109">La configuration de la messagerie de base de données à l’aide de l’ **Assistant Configuration de la messagerie de base de données** active les procédures stockées étendues de la messagerie de base de données dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="dcbb0-109">Configuring Database Mail using the **Database Mail Configuration Wizard** enables the Database Mail extended stored procedures in the **msdb** database.</span></span> <span data-ttu-id="dcbb0-110">Si vous utilisez l’ **Assistant Configuration de la messagerie de base de données**, il n’est pas nécessaire d’utiliser l’exemple **sp_configure** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="dcbb0-110">If you use the **Database Mail Configuration Wizard**, you do not have to use the **sp_configure** example below.</span></span>  
  
 <span data-ttu-id="dcbb0-111">Si l’option **Database Mail XPs** a la valeur 0, la messagerie de base de données ne démarre pas.</span><span class="sxs-lookup"><span data-stu-id="dcbb0-111">Setting the **Database Mail XPs** option to 0 prevents Database Mail from starting.</span></span> <span data-ttu-id="dcbb0-112">Si elle est en cours d’exécution lorsque la valeur 0 est affectée à l’option, elle continue de s’exécuter et d’envoyer des messages jusqu’à ce qu’elle soit inactive pendant la durée configurée dans l’option **DatabaseMailExeMinimumLifeTime** .</span><span class="sxs-lookup"><span data-stu-id="dcbb0-112">If it is running when the option is set to 0, it continues to run and send mail until it is idle for the time configured in the **DatabaseMailExeMinimumLifeTime** option.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="dcbb0-113">Exemples</span><span class="sxs-lookup"><span data-stu-id="dcbb0-113">Examples</span></span>  
 <span data-ttu-id="dcbb0-114">L'exemple suivant active les procédures stockées étendues de la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="dcbb0-114">The following example enables the Database Mail extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Database Mail XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcbb0-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dcbb0-115">See Also</span></span>  
 [<span data-ttu-id="dcbb0-116">Messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="dcbb0-116">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
