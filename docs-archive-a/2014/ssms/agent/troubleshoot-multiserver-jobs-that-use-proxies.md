---
title: Résoudre les problèmes liés aux travaux multiserveurs qui utilisent des proxys | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], multiserver jobs
- jobs [SQL Server Agent], multiserver jobs using proxies
ms.assetid: fc579bd3-010c-4f72-8b5c-d0cc18a1f280
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19de975ef5e1f22c93cec72a5014a01da5b03dd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699149"
---
# <a name="troubleshoot-multiserver-jobs-that-use-proxies"></a><span data-ttu-id="04380-102">Résoudre les problèmes liés aux travaux multiserveurs qui utilisent des proxys</span><span class="sxs-lookup"><span data-stu-id="04380-102">Troubleshoot Multiserver Jobs That Use Proxies</span></span>
  <span data-ttu-id="04380-103">Les travaux distribués dont les étapes sont associées à un proxy s'exécutent dans le contexte du compte proxy sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="04380-103">Distributed jobs whose steps are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="04380-104">Si les étapes de travail utilisant des comptes proxy échouent lors du téléchargement à partir du serveur maître, consultez la colonne **error_message** de la table **sysdownloadlist** dans la base de données **msdb** pour y rechercher les messages d’erreur suivants :</span><span class="sxs-lookup"><span data-stu-id="04380-104">If job steps that use proxy accounts fail when downloaded from the master server, check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="04380-105">« L'étape du travail nécessite un compte proxy, cependant la mise en correspondance de proxy est désactivée sur le serveur cible. »</span><span class="sxs-lookup"><span data-stu-id="04380-105">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="04380-106">Pour résoudre cette erreur, définissez le **\ HKEY_LOCAL_MACHINE \SOFTWARE\MICROSOFT\MICROSOFT SQL Server\MSSQL.** _ \<n_> Clé de Registre _**\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** sur **1 (true)**.</span><span class="sxs-lookup"><span data-stu-id="04380-106">To resolve this error, set the **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL.**_\<n_>**\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** registry subkey to **1 (true)**.</span></span> <span data-ttu-id="04380-107">Par défaut, cette sous-clé est définie sur **0** ( `false` ).</span><span class="sxs-lookup"><span data-stu-id="04380-107">By default, this subkey is set to **0** (`false`).</span></span> <span data-ttu-id="04380-108">Valeur de **MSSQL.**\<*n*></span><span class="sxs-lookup"><span data-stu-id="04380-108">The value of **MSSQL.**\<*n*></span></span> <span data-ttu-id="04380-109">est le nom de l’instance ; par exemple, **MSSQL. 1** ou **MSSQL. 3**.</span><span class="sxs-lookup"><span data-stu-id="04380-109">is the instance name; for example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
-   <span data-ttu-id="04380-110">« Proxy introuvable. »</span><span class="sxs-lookup"><span data-stu-id="04380-110">"Proxy not found."</span></span>  
  
     <span data-ttu-id="04380-111">Un compte proxy sur le serveur cible doit porter le même nom que le compte proxy de serveur maître avec lequel l'étape du travail s'exécute.</span><span class="sxs-lookup"><span data-stu-id="04380-111">To resolve this error, make sure a proxy account exists on the target server with the same name as the master server proxy account under which the job step runs.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04380-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="04380-112">See Also</span></span>  
 [<span data-ttu-id="04380-113">Créer un environnement multiserveur</span><span class="sxs-lookup"><span data-stu-id="04380-113">Create a Multiserver Environment</span></span>](create-a-multiserver-environment.md)  
  
  
