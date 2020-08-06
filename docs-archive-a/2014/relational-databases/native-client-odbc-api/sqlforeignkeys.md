---
title: SQLForeignKeys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLForeignKeys function
ms.assetid: 6c01ce0d-30d7-4c86-8705-3ab254d8a845
author: rothja
ms.author: jroth
ms.openlocfilehash: a61e80867abb8ecb4d2628b74dc9956051c8e4ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603528"
---
# <a name="sqlforeignkeys"></a><span data-ttu-id="6c177-102">SQLForeignKeys</span><span class="sxs-lookup"><span data-stu-id="6c177-102">SQLForeignKeys</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6c177-103">prend en charge les mises à jour en cascade et les suppressions via le mécanisme de contrainte de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="6c177-103">supports cascading updates and deletes through the foreign key constraint mechanism.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6c177-104">retourne SQL_CASCADE pour les colonnes UPDATE_RULE et/ou DELETE_RULE si l'option CASCADE est spécifiée dans la clause ON UPDATE et/ou ON DELETE des contraintes FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="6c177-104">returns SQL_CASCADE for UPDATE_RULE and/or DELETE_RULE columns if CASCADE option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6c177-105">retourne SQL_NO_ACTION pour les colonnes UPDATE_RULE et/ou DELETE_RULE si l'option NO ACTION est spécifiée dans la clause ON UPDATE et/ou ON DELETE des contraintes FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="6c177-105">returns SQL_NO_ACTION for UPDATE_RULE and/or DELETE_RULE columns if NO ACTION option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span>  
  
 <span data-ttu-id="6c177-106">Lorsque des valeurs non valides sont présentes dans un paramètre **SQLForeignKeys** , **SQLForeignKeys** retourne SQL_SUCCESS lors de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="6c177-106">When invalid values are present in any **SQLForeignKeys** parameter, **SQLForeignKeys** returns SQL_SUCCESS on execution.</span></span> <span data-ttu-id="6c177-107">**SQLFetch** retourne SQL_NO_DATA lorsque des valeurs non valides sont utilisées dans ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="6c177-107">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="6c177-108">**SQLForeignKeys** peut être exécuté sur un curseur côté serveur statique.</span><span class="sxs-lookup"><span data-stu-id="6c177-108">**SQLForeignKeys** can be executed on a static server cursor.</span></span> <span data-ttu-id="6c177-109">Une tentative d’exécution de **SQLForeignKeys** sur un curseur pouvant être mis à jour (dynamique ou de jeu de clés) retourne SQL_SUCCESS_WITH_INFO indiquant que le type de curseur a été modifié.</span><span class="sxs-lookup"><span data-stu-id="6c177-109">An attempt to execute **SQLForeignKeys** on an updatable (dynamic or keyset) cursor returns SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="6c177-110">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client prend en charge les informations de création de rapports pour les tables des serveurs liés en acceptant un nom en deux parties pour les paramètres *FKCatalogName* et *PKCatalogName* : *linked_server_name. catalog_name*.</span><span class="sxs-lookup"><span data-stu-id="6c177-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *FKCatalogName* and *PKCatalogName* parameters: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c177-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c177-111">See Also</span></span>  
 <span data-ttu-id="6c177-112">[SQLForeignKeys fonction)](https://go.microsoft.com/fwlink/?LinkId=59344) </span><span class="sxs-lookup"><span data-stu-id="6c177-112">[SQLForeignKeys Function](https://go.microsoft.com/fwlink/?LinkId=59344) </span></span>  
 [<span data-ttu-id="6c177-113">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="6c177-113">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
