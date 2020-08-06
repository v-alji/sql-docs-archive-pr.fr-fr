---
title: Capturer des données d’événement de déclencheur de connexion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e05b1ab4-c10b-402a-9591-f6ec1e3db8c0
author: rothja
ms.author: jroth
ms.openlocfilehash: b11323702d7468d07783b4d1c763dba691479d9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613905"
---
# <a name="capture-logon-trigger-event-data"></a><span data-ttu-id="7efe8-102">Capturer des données d'événements de déclencheurs de connexion</span><span class="sxs-lookup"><span data-stu-id="7efe8-102">Capture Logon Trigger Event Data</span></span>
  <span data-ttu-id="7efe8-103">Pour capturer des données XML relatives à des événements LOGON à utiliser dans des déclencheurs de connexion, utilisez la fonction [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="7efe8-103">To capture XML data about LOGON events for use inside logon triggers, use the [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) function.</span></span> <span data-ttu-id="7efe8-104">L'événement LOGON retourne le schéma des données d'événement suivant :</span><span class="sxs-lookup"><span data-stu-id="7efe8-104">The LOGON event returns the following event data schema:</span></span>  
  
 `<EVENT_INSTANCE>`  
  
 `<EventType>event_type</EventType>`  
  
 `<PostTime>post_time</PostTime>`  
  
 `<SPID>spid</SPID>`  
  
 `<ServerName>server_name</ServerName>`  
  
 `<LoginName>login_name</LoginName>`  
  
 `<LoginType>login_type</LoginType>`  
  
 `<SID>sid</SID>`  
  
 `<ClientHost>client_host</ClientHost>`  
  
 `<IsPooled>is_pooled</IsPooled>`  
  
 `</EVENT_INSTANCE>`  
  
 `<EventType>`  
 <span data-ttu-id="7efe8-105">Contient `LOGON`.</span><span class="sxs-lookup"><span data-stu-id="7efe8-105">Contains `LOGON`.</span></span>  
  
 `<PostTime>`  
 <span data-ttu-id="7efe8-106">Contient l'heure de demande d'établissement d'une session.</span><span class="sxs-lookup"><span data-stu-id="7efe8-106">Contains the time when a session is requested to be established.</span></span>  
  
 `<SID>`  
 <span data-ttu-id="7efe8-107">Contient le flux binaire encodé en base 64 du numéro d'identification de sécurité (SID) correspondant au nom de connexion spécifié.</span><span class="sxs-lookup"><span data-stu-id="7efe8-107">Contains the base 64-encoded binary stream of the security identification number (SID) for the specified login name.</span></span>  
  
 `<ClientHost>`  
 <span data-ttu-id="7efe8-108">Contient le nom d'hôte du client à partir duquel a été établie la connexion.</span><span class="sxs-lookup"><span data-stu-id="7efe8-108">Contains the host name of the client from where the connection is made.</span></span> <span data-ttu-id="7efe8-109">La valeur est '`<local_machine>`' si le nom du serveur et du client sont identiques.</span><span class="sxs-lookup"><span data-stu-id="7efe8-109">The value is '`<local_machine>`' if the client and server name are the same.</span></span> <span data-ttu-id="7efe8-110">Sinon, la valeur est l'adresse IP du client.</span><span class="sxs-lookup"><span data-stu-id="7efe8-110">Otherwise, the value is the IP address of the client.</span></span>  
  
 `<IsPooled>`  
 <span data-ttu-id="7efe8-111">Valeur égale à `1` si la connexion est réutilisée à l'aide du groupement de connexions.</span><span class="sxs-lookup"><span data-stu-id="7efe8-111">Is `1` if the connection is reused by using connection pooling.</span></span> <span data-ttu-id="7efe8-112">Sinon, la valeur est `0`.</span><span class="sxs-lookup"><span data-stu-id="7efe8-112">Otherwise, the value is `0`.</span></span>  
  
  
