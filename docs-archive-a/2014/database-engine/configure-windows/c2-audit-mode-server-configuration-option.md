---
title: C2 audit mode (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], C2 Audit Mode option
- C2 auditing
- C2 Audit Mode option
- recording attempts
ms.assetid: 5a8d73a6-c4f6-4967-ba11-ecbcfc90b9cc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3407a2a94a43adb2d3d3b52994093d6ed0c2e684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707867"
---
# <a name="c2-audit-mode-server-configuration-option"></a><span data-ttu-id="84365-102">C2 audit mode (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="84365-102">c2 audit mode Server Configuration Option</span></span>
  <span data-ttu-id="84365-103">Le mode d’audit C2 peut être configuré à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de l’option **c2 audit mode** dans **sp_configure**.</span><span class="sxs-lookup"><span data-stu-id="84365-103">C2 audit mode can be configured through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or with the **c2 audit mode** option in **sp_configure**.</span></span> <span data-ttu-id="84365-104">La sélection de cette option configure le serveur pour qu'il enregistre les tentatives d'accès aux instructions et aux objets ayant réussi et ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="84365-104">Selecting this option will configure the server to record both failed and successful attempts to access statements and objects.</span></span> <span data-ttu-id="84365-105">Ces informations peuvent vous aider à comprendre l'activité du système et à détecter les éventuelles violations de la stratégie de sécurité.</span><span class="sxs-lookup"><span data-stu-id="84365-105">This information can help you profile system activity and track possible security policy violations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="84365-106">La norme de sécurité C2 a été remplacée par la certification Critères communs.</span><span class="sxs-lookup"><span data-stu-id="84365-106">The C2 security standard has been superseded by Common Criteria Certification.</span></span> <span data-ttu-id="84365-107">Voir [common criteria compliance enabled (option de configuration de serveur)](common-criteria-compliance-enabled-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="84365-107">See the [common criteria compliance enabled Server Configuration Option](common-criteria-compliance-enabled-server-configuration-option.md).</span></span>  
  
## <a name="audit-log-file"></a><span data-ttu-id="84365-108">Fichier journal d'audit</span><span class="sxs-lookup"><span data-stu-id="84365-108">Audit Log File</span></span>  
 <span data-ttu-id="84365-109">Les données de mode d'audit C2 sont enregistrées dans un fichier dans le répertoire de données par défaut de l'instance.</span><span class="sxs-lookup"><span data-stu-id="84365-109">C2 audit mode data is saved in a file in the default data directory of the instance.</span></span> <span data-ttu-id="84365-110">Si le fichier journal d’audit atteint sa taille maximale de 200 mégaoctets (Mo), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crée un fichier, referme l’ancien et écrit tous les nouveaux enregistrements d’audit dans le nouveau fichier.</span><span class="sxs-lookup"><span data-stu-id="84365-110">If the audit log file reaches its size limit of 200 megabytes (MB), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will create a new file, close the old file, and write all new audit records to the new file.</span></span> <span data-ttu-id="84365-111">Cette opération se poursuit jusqu’à la saturation du répertoire des données d'audit ou la désactivation de l'audit.</span><span class="sxs-lookup"><span data-stu-id="84365-111">This process will continue until the audit data directory fills up or auditing is turned off.</span></span> <span data-ttu-id="84365-112">Pour déterminer l'état d'une trace C2, interrogez l'affichage catalogue sys.traces.</span><span class="sxs-lookup"><span data-stu-id="84365-112">To determine the status of a C2 trace, query the sys.traces catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="84365-113">Le mode d'audit C2 enregistre une grande quantité d'informations sur les événements dans le fichier journal, qui peut se remplir rapidement.</span><span class="sxs-lookup"><span data-stu-id="84365-113">C2 audit mode saves a large amount of event information to the log file, which can grow quickly.</span></span> <span data-ttu-id="84365-114">Si le répertoire des données où sont enregistrés les journaux arrive à saturation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'arrête de lui-même.</span><span class="sxs-lookup"><span data-stu-id="84365-114">If the data directory in which logs are being saved runs out of space, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will shut itself down.</span></span> <span data-ttu-id="84365-115">Si l’audit est configuré pour démarrer automatiquement, vous devez soit redémarrer l’instance avec l’indicateur **-f** (pour ignorer l’audit), soit libérer de l’espace disque pour le journal d’audit.</span><span class="sxs-lookup"><span data-stu-id="84365-115">If auditing is set to start automatically, you must either restart the instance with the **-f** flag (which bypasses auditing), or free up additional disk space for the audit log.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="84365-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="84365-116">Permissions</span></span>  
 <span data-ttu-id="84365-117">Nécessite l'appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="84365-117">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84365-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="84365-118">Example</span></span>  
 <span data-ttu-id="84365-119">L'exemple suivant active le mode d'audit C2.</span><span class="sxs-lookup"><span data-stu-id="84365-119">The following example turns on C2 audit mode.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
sp_configure 'c2 audit mode', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="84365-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84365-120">See Also</span></span>  
 <span data-ttu-id="84365-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="84365-121">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="84365-122">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84365-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="84365-123">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="84365-123">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
