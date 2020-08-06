---
title: Informations d’identification (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- principals [SQL Server], credentials
- schemas [SQL Server], credentials
- permissions [SQL Server], credentials
- groups [SQL Server], credentials
- ALTER ANY CREDENTIAL permission
- security [SQL Server], credentials
- authentication [SQL Server], credentials
- users [SQL Server], credentials
- credentials [SQL Server], about credentials
- credentials [SQL Server]
ms.assetid: c8df6022-e0b4-46b8-9670-3f86938d3177
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: faa2b5be7cf6918b5d5232763a96ed4dbbc89e51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612732"
---
# <a name="credentials-database-engine"></a><span data-ttu-id="f769e-102">Informations d'identification (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="f769e-102">Credentials (Database Engine)</span></span>
  <span data-ttu-id="f769e-103">Les informations d'identification correspondent à un enregistrement qui contient les informations d'authentification requises pour la connexion à une ressource en dehors de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f769e-103">A credential is a record that contains the authentication information (credentials) required to connect to a resource outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f769e-104">Ces informations sont utilisées en interne par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f769e-104">This information is used internally by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f769e-105">La plupart des informations d'identification contiennent un nom d'utilisateur et un mot de passe Windows.</span><span class="sxs-lookup"><span data-stu-id="f769e-105">Most credentials contain a Windows user name and password.</span></span>  
  
 <span data-ttu-id="f769e-106">Les informations stockées dans des informations d'identification permettent à un utilisateur connecté à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] par le biais de l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] d'accéder à des ressources en dehors de l'instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="f769e-106">The information stored in a credential enables a user who has connected to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by way of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to access resources outside the server instance.</span></span> <span data-ttu-id="f769e-107">Lorsque la source externe est Windows, l'utilisateur est authentifié en tant qu'utilisateur Windows, tel que spécifié dans les informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="f769e-107">When the external resource is Windows, the user is authenticated as the Windows user specified in the credential.</span></span> <span data-ttu-id="f769e-108">Un groupe d'informations d'identification peut être mappé à plusieurs connexions [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f769e-108">A single credential can be mapped to multiple [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="f769e-109">En revanche, une connexion [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] peut être mappée à un seul groupe d'informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="f769e-109">However, a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can be mapped to only one credential.</span></span>  
  
 <span data-ttu-id="f769e-110">Les informations d'identification système sont créées automatiquement et sont associées à des points de terminaison spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f769e-110">System credentials are created automatically and are associated with specific endpoints.</span></span> <span data-ttu-id="f769e-111">Le nom de ces informations d'identification système commence par deux signes dièse (##).</span><span class="sxs-lookup"><span data-stu-id="f769e-111">Names for system credentials start with two hash signs (##).</span></span>  
  
 <span data-ttu-id="f769e-112">Pour plus d’informations sur les informations d’identification, consultez l’affichage catalogue [sys. Credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="f769e-112">For more information about credentials, see the [sys.credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) catalog view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="f769e-113">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="f769e-113">Related Content</span></span>  
 <span data-ttu-id="f769e-114">[Créer des informations d’identification](../authentication-access/create-a-credential.md) [créer des informations d’identification &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="f769e-114">[Create a Credential](../authentication-access/create-a-credential.md) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span></span>  
  
 [<span data-ttu-id="f769e-115">Sécurisation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f769e-115">Securing SQL Server</span></span>](../securing-sql-server.md)  
  
  
