---
title: Afficher un journal d’audit SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- audits [SQL Server], viewing logs
- viewing audit logs
- logs [SQL Server], audit
ms.assetid: e8feaca0-7852-422b-895a-319b965d8d9b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 8f9902a4fc92ef0b35bae62eb80170762c52fdec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602023"
---
# <a name="view-a-sql-server-audit-log"></a><span data-ttu-id="6e9e5-102">Afficher un journal d'audit SQL Server</span><span class="sxs-lookup"><span data-stu-id="6e9e5-102">View a SQL Server Audit Log</span></span>
  <span data-ttu-id="6e9e5-103">Cette rubrique explique comment afficher un journal d'audit SQL Server dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e9e5-103">This topic describes how to view a SQL Server audit log in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6e9e5-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="6e9e5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6e9e5-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="6e9e5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6e9e5-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6e9e5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6e9e5-107">**Pour afficher un journal d'audit SQL Server, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="6e9e5-107">**To view a SQL Server audit log, using:**</span></span>  
  
     [<span data-ttu-id="6e9e5-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e9e5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6e9e5-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="6e9e5-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6e9e5-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6e9e5-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6e9e5-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="6e9e5-111">Permissions</span></span>  
 <span data-ttu-id="6e9e5-112">Nécessite l’autorisation `CONTROL SERVER`.</span><span class="sxs-lookup"><span data-stu-id="6e9e5-112">Requires the `CONTROL SERVER` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6e9e5-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e9e5-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-sql-server-audit-log"></a><span data-ttu-id="6e9e5-114">Pour afficher un journal d'audit SQL Server</span><span class="sxs-lookup"><span data-stu-id="6e9e5-114">To view a SQL Server audit log</span></span>  
  
1.  <span data-ttu-id="6e9e5-115">Dans l'Explorateur d'objets, développez le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="6e9e5-115">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="6e9e5-116">Développez le dossier **Audits** .</span><span class="sxs-lookup"><span data-stu-id="6e9e5-116">Expand the **Audits** folder.</span></span>  
  
3.  <span data-ttu-id="6e9e5-117">Cliquez avec le bouton droit sur le journal d’audit que vous souhaitez afficher et sélectionnez **Afficher les journaux d’audit**.</span><span class="sxs-lookup"><span data-stu-id="6e9e5-117">Right-click the audit log that you want to view and select **View Audit Logs**.</span></span> <span data-ttu-id="6e9e5-118">La boîte **de dialogue visionneuse du fichier journal-**_SERVER_NAME_ s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="6e9e5-118">This opens the **Log File Viewer -**_server_name_ dialog box.</span></span> <span data-ttu-id="6e9e5-119">Pour plus d'informations, consultez [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="6e9e5-119">For more information, see [Log File Viewer F1 Help](../../logs/log-file-viewer-f1-help.md).</span></span>  
  
4.  <span data-ttu-id="6e9e5-120">Lorsque vous avez terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="6e9e5-120">When finished, click **Close**.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="6e9e5-121">recommande d'afficher le journal d'audit à l'aide de la visionneuse du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="6e9e5-121">recommends viewing the audit log by using the Log File Viewer.</span></span> <span data-ttu-id="6e9e5-122">Toutefois, si vous créez un système de surveillance automatisé, les informations contenues dans le fichier d’audit peuvent être lues directement à l’aide de la fonction [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6e9e5-122">However, if you are creating an automated monitoring system, the information in the audit file can be read directly by using the [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql) function.</span></span> <span data-ttu-id="6e9e5-123">Si le fichier est lu directement, les données sont retournées dans un format légèrement différent (non traité).</span><span class="sxs-lookup"><span data-stu-id="6e9e5-123">Reading the file directly returns data in a slightly different (unprocessed) format.</span></span> <span data-ttu-id="6e9e5-124">Pour plus d’informations **, consultez sys. fn_get_audit_file**</span><span class="sxs-lookup"><span data-stu-id="6e9e5-124">See **sys.fn_get_audit_file** for more information</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9e5-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e9e5-125">See Also</span></span>  
 <span data-ttu-id="6e9e5-126">[SQL Server Audit &#40moteur de base de données&#41;](sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="6e9e5-126">[SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="6e9e5-127">Écrire des événements d’audit SQL Server dans le journal de sécurité</span><span class="sxs-lookup"><span data-stu-id="6e9e5-127">Write SQL Server Audit Events to the Security Log</span></span>](write-sql-server-audit-events-to-the-security-log.md)  
  
  
