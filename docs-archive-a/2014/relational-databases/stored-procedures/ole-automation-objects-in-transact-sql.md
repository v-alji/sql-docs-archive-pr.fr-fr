---
title: Objets OLE Automation dans Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], OLE Automation
- batches [SQL Server], OLE Automation
- OLE Automation [SQL Server]
- OLE Automation [SQL Server], about OLE Automation
ms.assetid: a887d956-4cd0-400a-aa96-00d7abd7c44b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f36846565bb60fbf875e9babdabbb6d1667f5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615120"
---
# <a name="ole-automation-objects-in-transact-sql"></a><span data-ttu-id="96136-102">Objets OLE Automation dans Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96136-102">OLE Automation Objects in Transact-SQL</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="96136-103">contient plusieurs procédures stockées système qui permettent aux objets OLE Automation d’être référencés dans les lots [!INCLUDE[tsql](../../includes/tsql-md.md)] , les procédures stockées et les déclencheurs.</span><span class="sxs-lookup"><span data-stu-id="96136-103">includes several system stored procedures that allow OLE Automation objects to be referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] batches, stored procedures, and triggers.</span></span> <span data-ttu-id="96136-104">Les procédures stockées système sont exécutées en tant que procédures stockées étendues, et les objets OLE Automation invoqués par les procédures stockées sont exécutés dans l'espace d'adressage d'une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] de la même façon que les procédures stockées étendues.</span><span class="sxs-lookup"><span data-stu-id="96136-104">These system stored procedures run as extended stored procedures, and the OLE Automation objects that are executed through the stored procedures run in the address space of an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in the same way that an extended stored procedure runs.</span></span>  
  
 <span data-ttu-id="96136-105">Les procédures stockées OLE Automation permettent aux lots [!INCLUDE[tsql](../../includes/tsql-md.md)] de faire référence aux objets SQL-DMO et aux objets OLE Automation personnalisés, notamment ceux qui exposent l’interface **IDispatch** .</span><span class="sxs-lookup"><span data-stu-id="96136-105">The OLE Automation stored procedures enable [!INCLUDE[tsql](../../includes/tsql-md.md)] batches to reference SQL-DMO objects and custom OLE Automation objects, such as objects that expose the **IDispatch** interface.</span></span> <span data-ttu-id="96136-106">Un serveur OLE In-process personnalisé qui est créé à l’aide de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] doit disposer d’un gestionnaire d’erreurs (spécifié avec l’instruction **On Error GoTo**) pour les sous-routines **Class_Initialize** et **Class_Terminate**.</span><span class="sxs-lookup"><span data-stu-id="96136-106">A custom in-process OLE server that is created by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] must have an error handler (specified with the **On Error GoTo** statement) for the **Class_Initialize** and **Class_Terminate** subroutines.</span></span> <span data-ttu-id="96136-107">Les erreurs non gérées dans les sous-routines **Class_Initialize** et **Class_Terminate** peuvent entraîner des erreurs imprévisibles, comme une violation d’accès dans une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96136-107">Unhandled errors in the **Class_Initialize** and **Class_Terminate** subroutines can cause unpredictable errors, such as an access violation in an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="96136-108">Les gestionnaires d'erreurs sont également recommandés pour les autres sous-routines.</span><span class="sxs-lookup"><span data-stu-id="96136-108">Error handlers for other subroutines are also recommended.</span></span>  
  
 <span data-ttu-id="96136-109">Pour utiliser un objet OLE Automation dans [!INCLUDE[tsql](../../includes/tsql-md.md)] , il est nécessaire d’appeler la procédure stockée système **sp_OACreate** pour créer une instance de cet objet dans l’espace d’adressage de l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96136-109">The first step when using an OLE Automation object in [!INCLUDE[tsql](../../includes/tsql-md.md)] is to call the **sp_OACreate** system stored procedure to create an instance of the object in the address space of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="96136-110">Lorsqu'une instance de l'objet a été créée, appelez les procédures stockées suivantes pour travailler avec les propriétés, méthodes et informations d'erreur de l'objet :</span><span class="sxs-lookup"><span data-stu-id="96136-110">After an instance of the object has been created, call the following stored procedures to work with the properties, methods, and error information related to the object:</span></span>  
  
-   <span data-ttu-id="96136-111">**sp_OAGetProperty** obtient la valeur d’une propriété.</span><span class="sxs-lookup"><span data-stu-id="96136-111">**sp_OAGetProperty** obtains the value of a property.</span></span>  
  
-   <span data-ttu-id="96136-112">**sp_OASetProperty** définit la valeur d’une propriété.</span><span class="sxs-lookup"><span data-stu-id="96136-112">**sp_OASetProperty** sets the value of a property.</span></span>  
  
-   <span data-ttu-id="96136-113">**sp_OAMethod** appelle une méthode.</span><span class="sxs-lookup"><span data-stu-id="96136-113">**sp_OAMethod** calls a method.</span></span>  
  
-   <span data-ttu-id="96136-114">**sp_OAGetErrorInfo** obtient les informations les plus récentes sur les erreurs.</span><span class="sxs-lookup"><span data-stu-id="96136-114">**sp_OAGetErrorInfo** obtains the most recent error information.</span></span>  
  
 <span data-ttu-id="96136-115">Quand l’objet est devenu inutile, appelez **sp_OADestroy** pour désallouer l’instance de l’objet créée avec **sp_OACreate**.</span><span class="sxs-lookup"><span data-stu-id="96136-115">When there is no more need for the object, call **sp_OADestroy** to deallocate the instance of the object created by using **sp_OACreate**.</span></span>  
  
 <span data-ttu-id="96136-116">Les objets OLE Automation retournent les données par l'intermédiaire de valeurs de propriétés et de méthodes.</span><span class="sxs-lookup"><span data-stu-id="96136-116">OLE Automation objects return data through property values and methods.</span></span> <span data-ttu-id="96136-117">**sp_OAGetProperty** et **sp_OAMethod** retournent ces valeurs de données sous forme d’un ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="96136-117">**sp_OAGetProperty** and **sp_OAMethod** return these data values in the form of a result set.</span></span>  
  
 <span data-ttu-id="96136-118">La portée d'un objet OLE Automation est un traitement.</span><span class="sxs-lookup"><span data-stu-id="96136-118">The scope of an OLE Automation object is a batch.</span></span> <span data-ttu-id="96136-119">Toutes les références à un objet doivent se trouver dans un seul traitement, une seule procédure stockée ou un seul déclencheur.</span><span class="sxs-lookup"><span data-stu-id="96136-119">All references to the object must be contained in a single batch, stored procedure, or trigger.</span></span>  
  
 <span data-ttu-id="96136-120">Lorsque des références à des objets sont faites, les objets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE Automation prennent en charge le passage à travers l'objet référencé pour atteindre les autres objets qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="96136-120">When it references objects, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE Automation objects support traversing the referenced object to other objects that it contains.</span></span> <span data-ttu-id="96136-121">Par exemple, quand l’objet SQL-DMO **SQLServer** est utilisé, il est possible de créer des références aux bases de données et aux tables qui se trouvent sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="96136-121">For example, when using the SQL-DMO **SQLServer** object, references can be made to databases and tables contained on that server.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="96136-122">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="96136-122">Related Content</span></span>  
 [<span data-ttu-id="96136-123">Syntaxe de hiérarchie des objets &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="96136-123">Object Hierarchy Syntax &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/object-hierarchy-syntax-transact-sql)  
  
 [<span data-ttu-id="96136-124">Configuration de la surface d'exposition</span><span class="sxs-lookup"><span data-stu-id="96136-124">Surface Area Configuration</span></span>](../security/surface-area-configuration.md)  
  
 [<span data-ttu-id="96136-125">Procédures OLE Automation (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="96136-125">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
 [<span data-ttu-id="96136-126">sp_OACreate &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="96136-126">sp_OACreate &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oacreate-transact-sql)  
  
 [<span data-ttu-id="96136-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="96136-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oagetproperty-transact-sql)  
  
 [<span data-ttu-id="96136-128">sp_OASetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="96136-128">sp_OASetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oasetproperty-transact-sql)  
  
 [<span data-ttu-id="96136-129">sp_OAMethod &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="96136-129">sp_OAMethod &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oamethod-transact-sql)  
  
 [<span data-ttu-id="96136-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="96136-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql)  
  
 [<span data-ttu-id="96136-131">sp_OADestroy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="96136-131">sp_OADestroy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oadestroy-transact-sql)  
  
  
