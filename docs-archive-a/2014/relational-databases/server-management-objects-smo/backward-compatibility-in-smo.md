---
title: Compatibilité descendante dans SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 2f986436-aaf2-4eaf-9809-df849d97d4fb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73b6f4eebccf23850ccf08ec95ccb59dbc5c6293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605366"
---
# <a name="backward-compatibility-in-smo"></a><span data-ttu-id="2c460-102">Compatibilité descendante dans SMO</span><span class="sxs-lookup"><span data-stu-id="2c460-102">Backward Compatibility in SMO</span></span>
  <span data-ttu-id="2c460-103">Les applications SMO écrites dans une version précédente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent être recompilées à l'aide de SMO dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c460-103">SMO applications that were written using previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be recompiled by using SMO in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="migrating-smo-applications"></a><span data-ttu-id="2c460-104">Migration d'applications SMO</span><span class="sxs-lookup"><span data-stu-id="2c460-104">Migrating SMO Applications</span></span>  
 <span data-ttu-id="2c460-105">Les références aux DLL SMO dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doivent être supprimées et celles aux nouvelles DLL SMO fournies avec [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] doivent être incluses.</span><span class="sxs-lookup"><span data-stu-id="2c460-105">References to SMO dlls in older versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed, and references to the new SMO dlls that are provided with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be included.</span></span>  
  
 <span data-ttu-id="2c460-106">Vous devez au minimum faire référence aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2c460-106">Minimally, you would reference the following:</span></span>  
  
-   <span data-ttu-id="2c460-107">Microsoft.SqlServer.ConnectionInfo</span><span class="sxs-lookup"><span data-stu-id="2c460-107">Microsoft.SqlServer.ConnectionInfo</span></span>  
  
-   <span data-ttu-id="2c460-108">Microsoft.SqlServer.Smo</span><span class="sxs-lookup"><span data-stu-id="2c460-108">Microsoft.SqlServer.Smo</span></span>  
  
-   <span data-ttu-id="2c460-109">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="2c460-109">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
 <span data-ttu-id="2c460-110">Ces fichiers sont requis pour les classes de connexion, les classes utilitaires SMO et les classes de base.</span><span class="sxs-lookup"><span data-stu-id="2c460-110">These files are required for connection classes, SMO utility classes, and foundation classes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c460-111">SmoEnum.dll ayant été supprimé, les références à ce fichier doivent être supprimées du projet SMO [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c460-111">SmoEnum.dll has been removed so references to it must be removed from the SMO [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] project.</span></span>  
  
 <span data-ttu-id="2c460-112">Les espaces de noms ayant également changé, vous pouvez utiliser les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2c460-112">The namespaces have also changed, so you can use the following:</span></span>  
  
##### <a name="for-visual-c"></a><span data-ttu-id="2c460-113">Pour Visual C#</span><span class="sxs-lookup"><span data-stu-id="2c460-113">For Visual C#</span></span>  
  
```  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
```  
  
##### <a name="for-visual-basic"></a><span data-ttu-id="2c460-114">Pour Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c460-114">For Visual Basic</span></span>  
  
```  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
```  
  
 <span data-ttu-id="2c460-115">Si votre code utilise une fonction Urn, telle que `Server.GetSqlSmoObject(Urn)`, vous devez établir un lien avec l'espace de noms Microsoft.SqlServer.Management.Sdk.Sfc.</span><span class="sxs-lookup"><span data-stu-id="2c460-115">If your code uses Urn functionality, such as `Server.GetSqlSmoObject(Urn)`, you must link to the Microsoft.SqlServer.Management.Sdk.Sfc namespace.</span></span>  
  
 <span data-ttu-id="2c460-116">Si votre code utilise directement l'objet de transfert, vous devrez établir un lien avec l'espace de noms Microsoft.SqlServer.Management.SmoExtended.</span><span class="sxs-lookup"><span data-stu-id="2c460-116">If your code uses the Transfer object directly, you will have to link to the Microsoft.SqlServer.Management.SmoExtended namespace.</span></span>  
  
 <span data-ttu-id="2c460-117">Lors de la migration du code, il est possible que vous deviez le modifier.</span><span class="sxs-lookup"><span data-stu-id="2c460-117">When you migrate code, you might have to modify the code.</span></span> <span data-ttu-id="2c460-118">En effet, plusieurs fonctionnalités [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ont été déconseillées dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c460-118">This is because several [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] features have been deprecated in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2c460-119">Pour plus d’informations sur les fonctionnalités déconseillées, consultez [fonctionnalités déconseillées de moteur de base de données dans SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) dans la [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation en ligne de.</span><span class="sxs-lookup"><span data-stu-id="2c460-119">For more information about deprecated features, see [Deprecated Database Engine Features in SQL Server 2014](../../database-engine/deprecated-database-engine-features-in-sql-server-2016.md) in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
