---
title: Utiliser les facettes de la gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- viewing Policy-Based Management facets
- facets [Policy-Based Management], copying
- facets [Policy-Based Management], viewing
- copying Policy-Based Management facets
ms.assetid: 88d025c4-07c2-4e4d-8634-204249a8c82c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5a356550796cc682b2292defffd6565b7fea0783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603424"
---
# <a name="working-with-policy-based-management-facets"></a><span data-ttu-id="814bc-102">Utiliser les facettes de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="814bc-102">Working with Policy-Based Management Facets</span></span>
  <span data-ttu-id="814bc-103">Une facette de la gestion basée sur des stratégies est un ensemble de propriétés logiques liées à une zone d'intérêt de gestion.</span><span class="sxs-lookup"><span data-stu-id="814bc-103">A Policy-Based Management facet is a set of logical properties that are related to an area of management interest.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="814bc-104">inclut plusieurs facettes prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="814bc-104">includes several predefined facets.</span></span> <span data-ttu-id="814bc-105">Par exemple, la facette Configuration de la surface d'exposition définit en tant que propriétés les fonctionnalités qui sont désactivées par défaut.</span><span class="sxs-lookup"><span data-stu-id="814bc-105">For example, the Surface Area Configuration facet defines, as properties, the features that are off by default.</span></span>  
  
 <span data-ttu-id="814bc-106">Lorsque vous gérez de nombreux environnements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] similaires, vous pouvez configurer une facette dans une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copier l’état de cette facette dans un fichier, puis importer ce fichier dans une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en tant que stratégie.</span><span class="sxs-lookup"><span data-stu-id="814bc-106">When you manage many similar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environments, you can configure a facet in one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copy the state of the facet to a file, and then import that file into another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a policy.</span></span> <span data-ttu-id="814bc-107">Une fois l'état converti en stratégie, cette stratégie peut être appliquée à d'autres instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], à des objets d'instance, à des bases de données ou à des objets de base de données.</span><span class="sxs-lookup"><span data-stu-id="814bc-107">When the state has been converted to a policy, the policy can be applied to other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance objects, databases, or database objects.</span></span>  
  
 <span data-ttu-id="814bc-108">Cette rubrique décrit comment copier l'état d'une facette dans un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="814bc-108">This topic describes how to copy the state of a facet to an XML file.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="814bc-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="814bc-109">Permissions</span></span>  
 <span data-ttu-id="814bc-110">Les procédures de cette rubrique nécessite l’appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="814bc-110">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
## <a name="viewing-and-copying-facet-states"></a><span data-ttu-id="814bc-111">Affichage et copie d'états de facette</span><span class="sxs-lookup"><span data-stu-id="814bc-111">Viewing and Copying Facet States</span></span>  
 [<span data-ttu-id="814bc-112">Afficher les facettes de la gestion basée sur des stratégies sur un objet SQL Server</span><span class="sxs-lookup"><span data-stu-id="814bc-112">View the Policy-Based Management Facets on a SQL Server Object</span></span>](view-the-policy-based-management-facets-on-a-sql-server-object.md)  
  
 [<span data-ttu-id="814bc-113">Copier un état de facette de la gestion basée sur des stratégies dans un fichier XML</span><span class="sxs-lookup"><span data-stu-id="814bc-113">Copy a Policy-Based Management Facet State to an XML File</span></span>](copy-a-policy-based-management-facet-state-to-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="814bc-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="814bc-114">See Also</span></span>  
 [<span data-ttu-id="814bc-115">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="814bc-115">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
