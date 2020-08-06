---
title: common criteria compliance enabled (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- common criteria compliance
helpviewer_keywords:
- CC (common criteria) [Database Engine]
- common criteria compliance [Database Engine]
- Risidual Information Protection [Database Engine]
- RIP (Residual Information Protection)
ms.assetid: 61766eea-c450-408d-af33-fbe7ef8c9ff2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6722d05351b8b9e80240abb4edef0633a97b6da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601102"
---
# <a name="common-criteria-compliance-enabled-server-configuration-option"></a><span data-ttu-id="2f508-102">common criteria compliance enabled (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="2f508-102">common criteria compliance enabled Server Configuration Option</span></span>
  <span data-ttu-id="2f508-103">L'option common criteria compliance enabled active les éléments suivants requis pour les critères communs.</span><span class="sxs-lookup"><span data-stu-id="2f508-103">The common criteria compliance enabled option enables the following elements that are required for the Common Criteria.</span></span>  
  
|<span data-ttu-id="2f508-104">Critères</span><span class="sxs-lookup"><span data-stu-id="2f508-104">Criteria</span></span>|<span data-ttu-id="2f508-105">Description</span><span class="sxs-lookup"><span data-stu-id="2f508-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="2f508-106">Protection des informations résiduelles (RIP, Residual Information Protection)</span><span class="sxs-lookup"><span data-stu-id="2f508-106">Residual Information Protection (RIP)</span></span>|<span data-ttu-id="2f508-107">RIP nécessite qu'une allocation mémoire soit remplacée par une séquence identifiée de bits avant que la mémoire ne soit réaffectée à une nouvelle ressource.</span><span class="sxs-lookup"><span data-stu-id="2f508-107">RIP requires a memory allocation to be overwritten with a known pattern of bits before memory is reallocated to a new resource.</span></span> <span data-ttu-id="2f508-108">Le fait de satisfaire à la norme RIP peut contribuer à améliorer la sécurité ; cependant, le remplacement de l'allocation mémoire peut ralentir les performances.</span><span class="sxs-lookup"><span data-stu-id="2f508-108">Meeting the RIP standard can contribute to improved security; however, overwriting the memory allocation can slow performance.</span></span> <span data-ttu-id="2f508-109">Après que l'option common criteria compliance enabled a été activée, le remplacement se produit.</span><span class="sxs-lookup"><span data-stu-id="2f508-109">After the common criteria compliance enabled option is enabled, the overwriting occurs.</span></span>|  
|<span data-ttu-id="2f508-110">Possibilité de consulter des statistiques de connexion</span><span class="sxs-lookup"><span data-stu-id="2f508-110">The ability to view login statistics</span></span>|<span data-ttu-id="2f508-111">Une fois que l'option common criteria compliance enabled a été activée, l'audit des connexions est activé.</span><span class="sxs-lookup"><span data-stu-id="2f508-111">After the common criteria compliance enabled option is enabled, login auditing is enabled.</span></span> <span data-ttu-id="2f508-112">Chaque fois qu'un utilisateur parvient à se connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il bénéficie d'informations sur l'heure de la dernière ouverture de session ayant abouti, l'heure de la dernière ouverture de session ayant échoué et le nombre de tentatives entre la dernière ouverture de session réussie et l'ouverture de session actuelle.</span><span class="sxs-lookup"><span data-stu-id="2f508-112">Each time a user successfully logs in to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], information about the last successful login time, the last unsuccessful login time, and the number of attempts between the last successful and current login times is made available.</span></span> <span data-ttu-id="2f508-113">Vous pouvez afficher ces statistiques de connexion en interrogeant la vue de gestion dynamique [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2f508-113">These login statistics can be viewed by querying the [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) dynamic management view.</span></span>|  
|<span data-ttu-id="2f508-114">La colonne GRANT ne doit pas remplacer la table DENY</span><span class="sxs-lookup"><span data-stu-id="2f508-114">That column GRANT should not override table DENY</span></span>|<span data-ttu-id="2f508-115">Après que l'option de conformité des critères communs a été activée, une option DENY au niveau table est prioritaire sur une option GRANT au niveau colonne.</span><span class="sxs-lookup"><span data-stu-id="2f508-115">After the common criteria compliance enabled option is enabled, a table-level DENY takes precedence over a column-level GRANT.</span></span> <span data-ttu-id="2f508-116">Quand l'option n'est pas activée, une option GRANT au niveau colonne est prioritaire sur une option DENY au niveau table.</span><span class="sxs-lookup"><span data-stu-id="2f508-116">When the option is not enabled, a column-level GRANT takes precedence over a table-level DENY.</span></span>|  
  
 <span data-ttu-id="2f508-117">L’option activée de conformité des critères communs est une option avancée.</span><span class="sxs-lookup"><span data-stu-id="2f508-117">The common criteria compliance enabled option is an advanced option.</span></span> <span data-ttu-id="2f508-118">Les critères communs sont évalués et certifiés uniquement pour l'édition Entreprise et Datacenter.</span><span class="sxs-lookup"><span data-stu-id="2f508-118">Common criteria is only evaluated and certified for the Enterprise edition and Datacenter edition.</span></span> <span data-ttu-id="2f508-119">Pour connaître l'état le plus récent de la certification des critères communs, consultez le site web [Critères communs de Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="2f508-119">For the latest status of common criteria certification, see the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f508-120">Vous devez non seulement activer l'option common criteria compliance enabled, mais également télécharger et exécuter un script qui achève la configuration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour assurer sa conformité à la norme Critères Communs au niveau d'évaluation 4+ (EAL4+).</span><span class="sxs-lookup"><span data-stu-id="2f508-120">In addition to enabling the common criteria compliance enabled option, you also must download and run a script that finishes configuring [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to comply with Common Criteria Evaluation Assurance Level 4+ (EAL4+).</span></span> <span data-ttu-id="2f508-121">Vous pouvez télécharger ce script à partir du site Web [Microsoft SQL Server Common Criteria (en anglais)](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="2f508-121">You can download this script from the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
 <span data-ttu-id="2f508-122">Si vous utilisez la procédure stockée système sp_configure pour changer sa valeur, vous ne pouvez modifier l'option de conformité aux critères communs que si la valeur 1 a été attribuée à l'option show advanced options.</span><span class="sxs-lookup"><span data-stu-id="2f508-122">If you are using the sp_configure system stored procedure to change the setting, you can change common criteria compliance enabled only when show advanced options is set to 1.</span></span> <span data-ttu-id="2f508-123">Le paramétrage prend effet une fois le serveur redémarré.</span><span class="sxs-lookup"><span data-stu-id="2f508-123">The setting takes effect after the server is restarted.</span></span> <span data-ttu-id="2f508-124">Les valeurs possibles sont 0 et 1 :</span><span class="sxs-lookup"><span data-stu-id="2f508-124">The possible values are 0 and 1:</span></span>  
  
-   <span data-ttu-id="2f508-125">0 signifie que la conformité des critères communs n'est pas activée.</span><span class="sxs-lookup"><span data-stu-id="2f508-125">0 indicates that common criteria compliance is not enabled.</span></span> <span data-ttu-id="2f508-126">Il s’agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="2f508-126">This is the default.</span></span>  
  
-   <span data-ttu-id="2f508-127">1 signifie que la conformité des critères communs est activée.</span><span class="sxs-lookup"><span data-stu-id="2f508-127">1 indicates that common criteria compliance is enabled.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2f508-128">Exemples</span><span class="sxs-lookup"><span data-stu-id="2f508-128">Examples</span></span>  
 <span data-ttu-id="2f508-129">L'exemple suivant active la conformité des critères communs.</span><span class="sxs-lookup"><span data-stu-id="2f508-129">The following example enables common criteria compliance.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'common criteria compliance enabled', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f508-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f508-130">See Also</span></span>  
 [<span data-ttu-id="2f508-131">Options de configuration de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2f508-131">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
