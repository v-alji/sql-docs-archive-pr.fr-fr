---
title: Sécurité au niveau des lignes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- row level security described
- row level security
- access control predicates
- security [SQL Server], predicate based access control
- predicate based security
ms.assetid: 7221fa4e-ca4a-4d5c-9f93-1b8a4af7b9e8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c67f84723e79b66d0454fb509f2fa9ced03dac7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697704"
---
# <a name="row-level-security"></a><span data-ttu-id="ba1ad-102">Sécurité au niveau des lignes</span><span class="sxs-lookup"><span data-stu-id="ba1ad-102">Row-Level Security</span></span>
  <span data-ttu-id="ba1ad-103">La sécurité au niveau des lignes permet aux clients de contrôler l’accès aux lignes d’une table de base de données en fonction des caractéristiques de l’utilisateur qui exécute une requête (par exemple, appartenance à un groupe ou contexte d’exécution).</span><span class="sxs-lookup"><span data-stu-id="ba1ad-103">Row-Level Security enables customers to control access to rows in a database table based on the characteristics of the user executing a query (e.g., group membership or execution context).</span></span> <span data-ttu-id="ba1ad-104">La sécurité au niveau de la ligne est désormais disponible dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016.</span><span class="sxs-lookup"><span data-stu-id="ba1ad-104">Row-Level Security is now available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016.</span></span> <span data-ttu-id="ba1ad-105">Consultez [Sécurité au niveau de la ligne](https://msdn.microsoft.com/library/dn765131.aspx) dans la documentation qui fournit la description actuelle de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ba1ad-105">See [Row-Level Security](https://msdn.microsoft.com/library/dn765131.aspx) in the current documentation for the current description of this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba1ad-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba1ad-106">See Also</span></span>  
 <span data-ttu-id="ba1ad-107">[CRÉER une stratégie de sécurité &#40;Azure SQL Database&#41;](/sql/t-sql/statements/create-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba1ad-107">[CREATE SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/create-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="ba1ad-108">[&#40;Azure SQL Database de la stratégie de sécurité ALTER&#41;](/sql/t-sql/statements/alter-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba1ad-108">[ALTER SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/alter-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="ba1ad-109">[SUPPRIMER les &#40;de la stratégie de sécurité Azure SQL Database&#41;](/sql/t-sql/statements/drop-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba1ad-109">[DROP SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/drop-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="ba1ad-110">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba1ad-110">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 <span data-ttu-id="ba1ad-111">[sys. security_policies &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-policies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba1ad-111">[sys.security_policies &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-policies-transact-sql) </span></span>  
 <span data-ttu-id="ba1ad-112">[sys. security_predicates &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-predicates-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba1ad-112">[sys.security_predicates &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-predicates-transact-sql) </span></span>  
 [<span data-ttu-id="ba1ad-113">Créer des fonctions définies par l’utilisateur &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="ba1ad-113">Create User-defined Functions &#40;Database Engine&#41;</span></span>](../user-defined-functions/create-user-defined-functions-database-engine.md)  
  
  
