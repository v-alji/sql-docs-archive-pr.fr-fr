---
title: clr enabled (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- assemblies [CLR integration], verifying can run
- clr enabled option
ms.assetid: 0722d382-8fd3-4fac-b4a8-cd2b7a7e0293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b83cd0e00bdd32c8b44667209544c8e81b1e90c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601100"
---
# <a name="clr-enabled-server-configuration-option"></a><span data-ttu-id="a09d1-102">clr enabled (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="a09d1-102">clr enabled Server Configuration Option</span></span>
  <span data-ttu-id="a09d1-103">L'option clr enabled vous permet de spécifier si des assemblys utilisateur peuvent être exécutés par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a09d1-103">Use the clr enabled option to specify whether user assemblies can be run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a09d1-104">L'option CLR activé fournit les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="a09d1-104">The clr enabled option provides the following values.</span></span>  
  
|<span data-ttu-id="a09d1-105">Valeur</span><span class="sxs-lookup"><span data-stu-id="a09d1-105">Value</span></span>|<span data-ttu-id="a09d1-106">Description</span><span class="sxs-lookup"><span data-stu-id="a09d1-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a09d1-107">0</span><span class="sxs-lookup"><span data-stu-id="a09d1-107">0</span></span>|<span data-ttu-id="a09d1-108">L'exécution de l'assembly n'est pas autorisée sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a09d1-108">Assembly execution not allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="a09d1-109">1</span><span class="sxs-lookup"><span data-stu-id="a09d1-109">1</span></span>|<span data-ttu-id="a09d1-110">L'exécution de l'assembly est autorisée sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a09d1-110">Assembly execution allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
 <span data-ttu-id="a09d1-111">Les serveurs WOW64 doivent redémarrer pour que les modifications apportées à ce paramètre prennent effet.</span><span class="sxs-lookup"><span data-stu-id="a09d1-111">WOW64 servers must be restarted before the changes to this setting will take effect.</span></span> <span data-ttu-id="a09d1-112">Le redémarrage n'est pas requis pour les autres types de serveurs.</span><span class="sxs-lookup"><span data-stu-id="a09d1-112">Restart is not required for other server types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a09d1-113">Lorsque l'instruction RECONFIGURE est exécutée et que la valeur d'exécution de l'option CLR activé est 0 et non plus 1, tous les domaines d'application contenant des assemblys utilisateur sont immédiatement déchargés.</span><span class="sxs-lookup"><span data-stu-id="a09d1-113">When RECONFIGURE is run and the run value of the clr enabled option is changed from 1 to 0, all application domains containing user assemblies are immediately unloaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a09d1-114">L'exécution du CLR (Common Language Runtime) n'est pas prise en charge sous l'option lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="a09d1-114">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="a09d1-115">Désactivez l'une des deux options suivantes : « clr enabled » ou « lightweight pooling ».</span><span class="sxs-lookup"><span data-stu-id="a09d1-115">Disable one of two options: "clr enabled" or "lightweight pooling.</span></span> <span data-ttu-id="a09d1-116">Les fonctionnalités qui reposent sur le CLR et qui ne fonctionnent pas correctement en mode fibre incluent le type de données `hierarchy`, la réplication et la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="a09d1-116">Features that rely upon CLR and that do not work properly in fiber mode include the `hierarchy` data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a09d1-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="a09d1-117">Example</span></span>  
 <span data-ttu-id="a09d1-118">L'exemple suivant déclare indique d'abord le paramètre actuel de l'option clr enabled, puis active l'option en lui attribuant la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="a09d1-118">The following example first displays the current setting of the clr enabled option and then enables the option by setting the option value to 1.</span></span> <span data-ttu-id="a09d1-119">Pour désactiver l'option, affectez-lui la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="a09d1-119">To disable the option, set the value to 0.</span></span>  
  
```  
EXEC sp_configure 'clr enabled';  
EXEC sp_configure 'clr enabled' , '1';  
RECONFIGURE;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="a09d1-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a09d1-120">See Also</span></span>  
 <span data-ttu-id="a09d1-121">[lightweight pooling (option de configuration de serveur)](lightweight-pooling-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="a09d1-121">[lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md) </span></span>  
 <span data-ttu-id="a09d1-122">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a09d1-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="a09d1-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a09d1-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="a09d1-124">lightweight pooling (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="a09d1-124">lightweight pooling Server Configuration Option</span></span>](lightweight-pooling-server-configuration-option.md)  
  
  
