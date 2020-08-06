---
title: OLE Automation Procedures (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Ole Automation Procedures option
ms.assetid: e8982e05-4984-4406-9760-285e8c028ddf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d34615ce1f808c1015c9c3d312a38a67dba291b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696043"
---
# <a name="ole-automation-procedures-server-configuration-option"></a><span data-ttu-id="cc2dd-102">OLE Automation Procedures (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="cc2dd-102">Ole Automation Procedures Server Configuration Option</span></span>
  <span data-ttu-id="cc2dd-103">Utilisez l'option `Ole Automation Procedures` pour spécifier si les objets OLE Automation peuvent être instanciés dans des traitements [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc2dd-103">Use the `Ole Automation Procedures` option to specify whether OLE Automation objects can be instantiated within [!INCLUDE[tsql](../../includes/tsql-md.md)] batches.</span></span> <span data-ttu-id="cc2dd-104">Cette option peut également être configurée à l’aide de la gestion basée sur une stratégie ou de la procédure stockée **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="cc2dd-104">This option can also be configured using the Policy-Based Management or the **sp_configure** stored procedure.</span></span> <span data-ttu-id="cc2dd-105">Pour plus d'informations, consultez [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="cc2dd-105">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
 <span data-ttu-id="cc2dd-106">L'option `Ole Automation Procedures` peut prendre les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="cc2dd-106">The `Ole Automation Procedures` option can be set to the following values.</span></span>  
  
 <span data-ttu-id="cc2dd-107">0</span><span class="sxs-lookup"><span data-stu-id="cc2dd-107">0</span></span>  
 <span data-ttu-id="cc2dd-108">Option Ole Automation Procedures désactivée.</span><span class="sxs-lookup"><span data-stu-id="cc2dd-108">OLE Automation Procedures are disabled.</span></span> <span data-ttu-id="cc2dd-109">Il s'agit de la valeur par défaut des nouvelles instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc2dd-109">Default for new instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cc2dd-110">1</span><span class="sxs-lookup"><span data-stu-id="cc2dd-110">1</span></span>  
 <span data-ttu-id="cc2dd-111">Option Ole Automation Procedures activée.</span><span class="sxs-lookup"><span data-stu-id="cc2dd-111">OLE Automation Procedures are enabled.</span></span>  
  
 <span data-ttu-id="cc2dd-112">Lorsque l’option Procédures OLE Automation est activée, un appel à **sp_OACreate** entraîne le démarrage de l’environnement d’exécution partagé OLE.</span><span class="sxs-lookup"><span data-stu-id="cc2dd-112">When OLE Automation Procedures are enabled, a call to **sp_OACreate** will start the OLE shared execution environment.</span></span>  
  
 <span data-ttu-id="cc2dd-113">La valeur actuelle de l' `Ole Automation Procedures` option peut être affichée et modifiée à l’aide de la procédure stockée système **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="cc2dd-113">The current value of the `Ole Automation Procedures` option can be viewed and changed by using the **sp_configure** system stored procedure.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cc2dd-114">Exemples</span><span class="sxs-lookup"><span data-stu-id="cc2dd-114">Examples</span></span>  
 <span data-ttu-id="cc2dd-115">L'exemple suivant illustre l'affichage de la valeur actuelle de l'option Ole Automation Procedures.</span><span class="sxs-lookup"><span data-stu-id="cc2dd-115">The following example shows how to view the current setting of OLE Automation procedures.</span></span>  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 <span data-ttu-id="cc2dd-116">L'exemple suivant illustre l'activation de l'option Ole Automation Procedures.</span><span class="sxs-lookup"><span data-stu-id="cc2dd-116">The following example shows how to enable OLE Automation procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc2dd-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc2dd-117">See Also</span></span>  
 <span data-ttu-id="cc2dd-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc2dd-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="cc2dd-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cc2dd-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="cc2dd-120">[Configuration de la surface d'exposition](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="cc2dd-120">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 [<span data-ttu-id="cc2dd-121">Options de configuration de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cc2dd-121">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
