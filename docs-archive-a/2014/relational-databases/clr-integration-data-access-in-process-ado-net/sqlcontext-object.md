---
title: Objet SqlContext | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- Windows identity [CLR integration]
- SqlContext object
- context [CLR integration]
ms.assetid: 67437853-8a55-44d9-9337-90689ebba730
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f036e274925f7b28b79f619f8e24b3e8804140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702987"
---
# <a name="sqlcontext-object"></a><span data-ttu-id="dbe45-102">Objet SqlContext</span><span class="sxs-lookup"><span data-stu-id="dbe45-102">SqlContext Object</span></span>
  <span data-ttu-id="dbe45-103">Vous appelez le code managé dans le serveur lorsque vous appelez une procédure ou une fonction, lorsque vous appelez une méthode sur un type CLR défini par l'utilisateur ou lorsque votre action active un déclencheur défini dans l'un des langages du [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dbe45-103">You invoke managed code in the server when you call a procedure or function, when you call a method on a common language runtime (CLR) user-defined type, or when your action fires a trigger defined in any of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework languages.</span></span> <span data-ttu-id="dbe45-104">Comme l'exécution de ce code est demandée dans le cadre d'une connexion utilisateur, l'accès au contexte de l'appelant à partir du code en cours d'exécution dans le serveur est requis.</span><span class="sxs-lookup"><span data-stu-id="dbe45-104">Because execution of this code is requested as part of a user connection, access to the context of the caller from the code running in the server is required.</span></span> <span data-ttu-id="dbe45-105">De plus, certaines opérations d'accès aux données ne peuvent être valides que si elles sont exécutées sous le contexte de l'appelant.</span><span class="sxs-lookup"><span data-stu-id="dbe45-105">In addition, certain data access operations may only be valid if run under the context of the caller.</span></span> <span data-ttu-id="dbe45-106">Par exemple, l'accès à des pseudo-tables insérées et supprimées utilisées dans les opérations de déclencheur n'est valide que sous le contexte de l'appelant.</span><span class="sxs-lookup"><span data-stu-id="dbe45-106">For example, access to inserted and deleted pseudo-tables used in trigger operations is only valid under the context of the caller.</span></span>  
  
 <span data-ttu-id="dbe45-107">Le contexte de l'appelant est soustrait dans un objet `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="dbe45-107">The context of the caller is abstracted in a `SqlContext` object.</span></span> <span data-ttu-id="dbe45-108">Pour plus d'informations sur les méthodes et les propriétés `SqlTriggerContext`, consultez la documentation de référence sur la classe `Microsoft.SqlServer.Server.SqlTriggerContext` dans le Kit de développement [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="dbe45-108">For more information about the `SqlTriggerContext` methods and properties, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="dbe45-109">`SqlContext` fournit l'accès aux composants suivants :</span><span class="sxs-lookup"><span data-stu-id="dbe45-109">`SqlContext` provides access to the following components:</span></span>  
  
-   <span data-ttu-id="dbe45-110">`SqlPipe` : l'objet `SqlPipe` représente le « canal » à travers lequel les résultats transitent vers le client.</span><span class="sxs-lookup"><span data-stu-id="dbe45-110">`SqlPipe`: The `SqlPipe` object represents the "pipe" through which results flow to the client.</span></span> <span data-ttu-id="dbe45-111">Pour plus d’informations sur l' `SqlPipe` objet, consultez l' [objet SqlPipe](sqlpipe-object.md).</span><span class="sxs-lookup"><span data-stu-id="dbe45-111">For more information about the `SqlPipe` object, see [SqlPipe Object](sqlpipe-object.md).</span></span>  
  
-   <span data-ttu-id="dbe45-112">`SqlTriggerContext` : l'objet `SqlTriggerContext` ne peut être extrait qu'à partir d'un déclencheur CLR.</span><span class="sxs-lookup"><span data-stu-id="dbe45-112">`SqlTriggerContext`: The `SqlTriggerContext` object can only be retrieved from within a CLR trigger.</span></span> <span data-ttu-id="dbe45-113">Il fournit des informations sur l'opération qui a provoqué l'activation du déclencheur et un mappage des colonnes mises à jour.</span><span class="sxs-lookup"><span data-stu-id="dbe45-113">It provides information about the operation that caused the trigger to fire and a map of the columns that were updated.</span></span> <span data-ttu-id="dbe45-114">Pour plus d’informations sur l' `SqlTriggerContext` objet, consultez [objet SqlTriggerContext](sqltriggercontext-object.md).</span><span class="sxs-lookup"><span data-stu-id="dbe45-114">For more information about the `SqlTriggerContext` object, see [SqlTriggerContext Object](sqltriggercontext-object.md).</span></span>  
  
-   <span data-ttu-id="dbe45-115">`IsAvailable` : la propriété `IsAvailable` est utilisée pour déterminer la disponibilité du contexte.</span><span class="sxs-lookup"><span data-stu-id="dbe45-115">`IsAvailable`: The `IsAvailable` property is used to determine context availability.</span></span>  
  
-   <span data-ttu-id="dbe45-116">`WindowsIdentity` : la propriété `WindowsIdentity` est utilisée pour extraire l'identité Windows de l'appelant.</span><span class="sxs-lookup"><span data-stu-id="dbe45-116">`WindowsIdentity`: The `WindowsIdentity` property is used to retrieve the Windows identity of the caller.</span></span>  
  
## <a name="determining-context-availability"></a><span data-ttu-id="dbe45-117">Détermination de la disponibilité du contexte</span><span class="sxs-lookup"><span data-stu-id="dbe45-117">Determining Context Availability</span></span>  
 <span data-ttu-id="dbe45-118">Interrogez la classe `SqlContext` pour voir si le code en cours s'exécute in-process.</span><span class="sxs-lookup"><span data-stu-id="dbe45-118">Query the `SqlContext` class to see if the currently executing code is running in-process.</span></span> <span data-ttu-id="dbe45-119">À cette fin, vérifiez la propriété `IsAvailable` de l'objet `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="dbe45-119">To do this, check the `IsAvailable` property of the `SqlContext` object.</span></span> <span data-ttu-id="dbe45-120">La propriété `IsAvailable` est en lecture seule, et retourne `True` si le code appelant s'exécute à l'intérieur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et si d'autres membres `SqlContext` peuvent être accédés.</span><span class="sxs-lookup"><span data-stu-id="dbe45-120">The `IsAvailable` property is read-only, and returns `True` if the calling code is running inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and if other `SqlContext` members can be accessed.</span></span> <span data-ttu-id="dbe45-121">Si la propriété `IsAvailable` retourne `False`, tous les autres membres `SqlContext` lèvent une exception `InvalidOperationException`, en cas d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="dbe45-121">If the `IsAvailable` property returns `False`, all the other `SqlContext` members throw an `InvalidOperationException`, if used.</span></span> <span data-ttu-id="dbe45-122">Si `IsAvailable` retourne `False`, toute tentative d'ouvrir un objet de connexion dont la chaîne de connexion contient "context connection=true" échoue.</span><span class="sxs-lookup"><span data-stu-id="dbe45-122">If `IsAvailable` returns `False`, any attempt to open a connection object that has "context connection=true" in the connection string fails.</span></span>  
  
## <a name="retrieving-windows-identity"></a><span data-ttu-id="dbe45-123">Extraction de l'identité Windows</span><span class="sxs-lookup"><span data-stu-id="dbe45-123">Retrieving Windows Identity</span></span>  
 <span data-ttu-id="dbe45-124">Le code CLR qui s'exécute à l'intérieur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est toujours appelé dans le contexte du compte de processus.</span><span class="sxs-lookup"><span data-stu-id="dbe45-124">CLR code executing inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is always invoked in the context of the process account.</span></span> <span data-ttu-id="dbe45-125">S'il est nécessaire que le code exécute certaines actions à l'aide de l'identité de l'utilisateur appelant plutôt qu'à l'aide de l'identité du processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un jeton d'emprunt d'identité doit être obtenu par le biais de la propriété `WindowsIdentity` de l'objet `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="dbe45-125">If the code should perform certain actions using the identity of the calling user, instead of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process identity, then an impersonation token should be obtained through the `WindowsIdentity` property of the `SqlContext` object.</span></span> <span data-ttu-id="dbe45-126">La propriété `WindowsIdentity` retourne une instance `WindowsIdentity` représentant l'identité [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows de l'appelant ou null si le client a été authentifié par le biais de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbe45-126">The `WindowsIdentity` property returns a `WindowsIdentity` instance representing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows identity of the caller, or null if the client was authenticated using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="dbe45-127">Seuls les assemblys marqués avec les autorisations `EXTERNAL_ACCESS` ou `UNSAFE` peuvent accéder à cette propriété.</span><span class="sxs-lookup"><span data-stu-id="dbe45-127">Only assemblies marked with `EXTERNAL_ACCESS` or `UNSAFE` permissions can access this property.</span></span>  
  
 <span data-ttu-id="dbe45-128">Après avoir obtenu l'objet `WindowsIdentity`, les appelants peuvent emprunter l'identité du compte client et effectuer des actions à sa place.</span><span class="sxs-lookup"><span data-stu-id="dbe45-128">After obtaining the `WindowsIdentity` object, callers can impersonate the client account and perform actions on their behalf.</span></span>  
  
 <span data-ttu-id="dbe45-129">L'identité de l'appelant est uniquement disponible via `SqlContext.WindowsIdentity` si le client qui a initié l'exécution de la procédure stockée ou de la fonction s'est connecté au serveur à l'aide de l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="dbe45-129">The identity of the caller is only available through `SqlContext.WindowsIdentity` if the client that initiated execution of the stored-procedure or function connected to the server using Windows Authentication.</span></span> <span data-ttu-id="dbe45-130">Si l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été utilisé à la place, cette propriété a la valeur Null et le code ne peut pas emprunter l'identité de l'appelant.</span><span class="sxs-lookup"><span data-stu-id="dbe45-130">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication was used instead, this property is null and the code is unable to impersonate the caller.</span></span>  
  
### <a name="example"></a><span data-ttu-id="dbe45-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="dbe45-131">Example</span></span>  
 <span data-ttu-id="dbe45-132">L'exemple suivant montre comment obtenir l'identité Windows du client appelant et emprunter l'identité du client.</span><span class="sxs-lookup"><span data-stu-id="dbe45-132">The following example shows how to get the Windows identity of the calling client and impersonate the client.</span></span>  
  
 <span data-ttu-id="dbe45-133">C#</span><span class="sxs-lookup"><span data-stu-id="dbe45-133">C#</span></span>  
  
```  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void WindowsIDTestProc()  
{  
    WindowsIdentity clientId = null;  
    WindowsImpersonationContext impersonatedUser = null;  
  
    // Get the client ID.  
    clientId = SqlContext.WindowsIdentity;  
  
    // This outer try block is used to thwart exception filter   
    // attacks which would prevent the inner finally   
    // block from executing and resetting the impersonation.  
    try  
    {  
        try  
        {  
            impersonatedUser = clientId.Impersonate();  
            if (impersonatedUser != null)  
            {  
                // Perform some action using impersonation.  
            }  
        }  
        finally  
        {  
            // Undo impersonation.  
            if (impersonatedUser != null)  
                impersonatedUser.Undo();  
        }  
    }  
    catch  
    {  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="dbe45-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dbe45-134">Visual Basic</span></span>  
  
```  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  WindowsIDTestProcVB ()  
    Dim clientId As WindowsIdentity  
    Dim impersonatedUser As WindowsImpersonationContext  
  
    ' Get the client ID.  
    clientId = SqlContext.WindowsIdentity  
  
    ' This outer try block is used to thwart exception filter   
    ' attacks which would prevent the inner finally   
    ' block from executing and resetting the impersonation.  
  
    Try  
        Try  
  
            impersonatedUser = clientId.Impersonate()  
  
            If impersonatedUser IsNot Nothing Then  
                ' Perform some action using impersonation.  
            End If  
  
        Finally  
            ' Undo impersonation.  
            If impersonatedUser IsNot Nothing Then  
                impersonatedUser.Undo()  
            End If  
        End Try  
  
    Catch e As Exception  
  
        Throw e  
  
    End Try  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="dbe45-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbe45-135">See Also</span></span>  
 <span data-ttu-id="dbe45-136">[SqlPipe, objet](sqlpipe-object.md) </span><span class="sxs-lookup"><span data-stu-id="dbe45-136">[SqlPipe Object](sqlpipe-object.md) </span></span>  
 <span data-ttu-id="dbe45-137">[Objet SqlTriggerContext](sqltriggercontext-object.md) </span><span class="sxs-lookup"><span data-stu-id="dbe45-137">[SqlTriggerContext Object](sqltriggercontext-object.md) </span></span>  
 <span data-ttu-id="dbe45-138">[Déclencheurs CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="dbe45-138">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="dbe45-139">Extensions spécifiques in-process de SQL Server à ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dbe45-139">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
