---
title: Emprunt d’identité et informations d’identification pour les connexions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- impersonation [CLR integration]
- security [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- authentication [CLR integration]
- user impersonation [CLR integration]
- credentials [CLR integration]
- database objects [CLR integration], security
ms.assetid: 293dce7d-1db2-4657-992f-8c583d6e9ebb
author: rothja
ms.author: jroth
ms.openlocfilehash: cdbc52e07f4502adda7301ce7f635c050ed9c3c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611117"
---
# <a name="impersonation-and-credentials-for-connections"></a><span data-ttu-id="2a483-102">Emprunt d'identité et informations d'identification pour les connexions</span><span class="sxs-lookup"><span data-stu-id="2a483-102">Impersonation and Credentials for Connections</span></span>
  <span data-ttu-id="2a483-103">Dans l'intégration du CLR (Common Language Runtime) [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'authentification Windows est complexe à utiliser, mais elle offre une protection supérieure à l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2a483-103">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] common language runtime (CLR) integration, using Windows Authentication is complex, but is more secure than using SQL Server Authentication.</span></span> <span data-ttu-id="2a483-104">Lorsque vous utilisez l'authentification Windows, gardez à l'esprit les points suivants.</span><span class="sxs-lookup"><span data-stu-id="2a483-104">When using Windows Authentication, keep in mind the following considerations.</span></span>  
  
 <span data-ttu-id="2a483-105">Par défaut, un processus SQL Server qui se connecte à Windows acquiert le contexte de sécurité du compte de service Windows SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2a483-105">By default, a SQL Server process that connects out to Windows acquires the security context of the SQL Server Windows service account.</span></span> <span data-ttu-id="2a483-106">Mais il est possible de mapper une fonction CLR à une identité de proxy afin que ses connexions sortantes aient un contexte de sécurité différent de celui du compte de service Windows.</span><span class="sxs-lookup"><span data-stu-id="2a483-106">But it is possible to map a CLR function to a proxy identity, so that its outbound connections have a different security context than that of the Windows service account.</span></span>  
  
 <span data-ttu-id="2a483-107">Dans certains cas, vous pouvez emprunter l'identité de l'appelant à l'aide de la propriété `SqlContext.WindowsIdentity` plutôt que de fonctionner en tant que compte de service.</span><span class="sxs-lookup"><span data-stu-id="2a483-107">In some cases, you may want to impersonate the caller by using the `SqlContext.WindowsIdentity` property instead of running as the service account.</span></span> <span data-ttu-id="2a483-108">L'instance de `WindowsIdentity`, qui représente l'identité du client qui a appelé le code appelant, est uniquement disponible lorsque le client utilise l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="2a483-108">The `WindowsIdentity` instance represents the identity of the client that invoked the calling code, and is only available when the client used Windows Authentication.</span></span> <span data-ttu-id="2a483-109">Après avoir obtenu l'instance de `WindowsIdentity`, vous pouvez appeler `Impersonate` pour modifier le jeton de sécurité du thread, puis ouvrir des connexions ADO.NET pour le compte du client.</span><span class="sxs-lookup"><span data-stu-id="2a483-109">After you have obtained the `WindowsIdentity` instance, you can call `Impersonate` to change the security token of the thread, and then open ADO.NET connections on behalf of the client.</span></span>  
  
 <span data-ttu-id="2a483-110">Une fois que vous avez appelé SQLContext. WindowsIdentity. Impersonate, vous ne pouvez pas accéder aux données locales et vous ne pouvez pas accéder aux données système.</span><span class="sxs-lookup"><span data-stu-id="2a483-110">After you call SQLContext.WindowsIdentity.Impersonate, you cannot access local data and you cannot access system data.</span></span> <span data-ttu-id="2a483-111">Pour accéder à nouveau aux données, vous devez appeler WindowsImpersonationContext. Undo.</span><span class="sxs-lookup"><span data-stu-id="2a483-111">To access data again, you have to call WindowsImpersonationContext.Undo.</span></span>  
  
 <span data-ttu-id="2a483-112">L'exemple suivant montre comment emprunter l'identité de l'appelant à l'aide de la propriété `SqlContext.WindowsIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2a483-112">The following example shows how to impersonate the caller by using the `SqlContext.WindowsIdentity` property.</span></span>  
  
 <span data-ttu-id="2a483-113">Visual C#</span><span class="sxs-lookup"><span data-stu-id="2a483-113">Visual C#</span></span>  
  
```  
WindowsIdentity clientId = null;  
WindowsImpersonationContext impersonatedUser = null;  
  
clientId = SqlContext.WindowsIdentity;  
  
// This outer try block is used to protect from   
// exception filter attacks which would prevent  
// the inner finally block from executing and   
// resetting the impersonation.  
try  
{  
   try  
   {  
      impersonatedUser = clientId.Impersonate();  
      if (impersonatedUser != null)  
         return GetFileDetails(directoryPath);  
         else return null;  
   }  
   finally  
   {  
      if (impersonatedUser != null)  
         impersonatedUser.Undo();  
   }  
}  
catch  
{  
   throw;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2a483-114">Pour plus d’informations sur les changements de comportement dans l’emprunt d’identité, consultez [modifications critiques apportées aux fonctionnalités de moteur de base de données dans SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="2a483-114">For information about behavior changes in impersonation, see [Breaking Changes to Database Engine Features in SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="2a483-115">Par ailleurs, si vous avez obtenu l'instance de l'identité [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows, vous ne pouvez pas, par défaut, propager cette instance à un autre ordinateur, cette opération étant restreinte par défaut par l'infrastructure de sécurité Windows.</span><span class="sxs-lookup"><span data-stu-id="2a483-115">Furthermore, if you obtained the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows identity instance, by default you cannot propagate that instance to another computer; Windows security infrastructure restricts that by default.</span></span> <span data-ttu-id="2a483-116">Il existe cependant un mécanisme, appelé « délégation », qui permet la propagation d'identités Windows sur plusieurs ordinateurs approuvés.</span><span class="sxs-lookup"><span data-stu-id="2a483-116">There is, however, a mechanism called "delegation" that enables propagation of Windows identities across multiple trusted computers.</span></span> <span data-ttu-id="2a483-117">Pour plus d’informations sur la délégation, consultez l’article TechNet «[transition de protocole Kerberos et délégation avec restriction](https://go.microsoft.com/fwlink/?LinkId=50419)».</span><span class="sxs-lookup"><span data-stu-id="2a483-117">You can learn more about delegation in the TechNet article, "[Kerberos Protocol Transition and Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=50419)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a483-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a483-118">See Also</span></span>  
 [<span data-ttu-id="2a483-119">Objet SqlContext</span><span class="sxs-lookup"><span data-stu-id="2a483-119">SqlContext Object</span></span>](../../clr-integration-data-access-in-process-ado-net/sqlcontext-object.md)  
  
  
