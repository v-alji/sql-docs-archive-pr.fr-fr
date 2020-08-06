---
title: Métadonnées de paramètre table pour les instructions préparées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), metadata for prepared statements
ms.assetid: fd2fc705-2e98-4011-9822-c7e6cca4a535
author: rothja
ms.author: jroth
ms.openlocfilehash: ad1394bd5e5bedc69a98308ba67a98434559c146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709304"
---
# <a name="table-valued-parameter-metadata-for-prepared-statements"></a><span data-ttu-id="a7122-102">Métadonnées de paramètre table pour les instructions préparées</span><span class="sxs-lookup"><span data-stu-id="a7122-102">Table-Valued Parameter Metadata for Prepared Statements</span></span>
  <span data-ttu-id="a7122-103">Une application peut obtenir des métadonnées pour un appel de procédure préparée par le biais de SQLNumParams et SQLDescribeParam.</span><span class="sxs-lookup"><span data-stu-id="a7122-103">An application can obtain metadata for a prepared procedure call through SQLNumParams and SQLDescribeParam.</span></span> <span data-ttu-id="a7122-104">Pour les paramètres table, *DataTypePtr* a la valeur SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="a7122-104">For table-valued parameters, *DataTypePtr* is set to SQL_SS_TABLE.</span></span> <span data-ttu-id="a7122-105">Des métadonnées supplémentaires sont disponibles via SQLGetDescField pour SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME et SQL_CA_SS_SCHEMA_NAME.</span><span class="sxs-lookup"><span data-stu-id="a7122-105">Additional metadata is available through SQLGetDescField for SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME.</span></span>  
  
 <span data-ttu-id="a7122-106">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME et SQL_CA_SS_SCHEMA_NAME peuvent être utilisés avec SQLColumns pour obtenir les métadonnées de colonne pour les types de tables associés aux paramètres table.</span><span class="sxs-lookup"><span data-stu-id="a7122-106">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME can be used with SQLColumns to obtain column metadata for table types associated with table-valued parameters.</span></span> <span data-ttu-id="a7122-107">Dans ce cas, SQL_SOPT_SS_NAME_SCOPE doit être défini sur SQL_SS_NAME_SCOPE_TABLE_TYPE avant l’appel de SQLColumns.</span><span class="sxs-lookup"><span data-stu-id="a7122-107">In this case, SQL_SOPT_SS_NAME_SCOPE must be set to SQL_SS_NAME_SCOPE_TABLE_TYPE before SQLColumns is called.</span></span> <span data-ttu-id="a7122-108">SQL_SOPT_SS_NAME_SCOPE doit ensuite de nouveau être défini sur la valeur par défaut, SQL_SS_NAME_SCOPE_TABLE, lorsque l'application a terminé de récupérer les métadonnées de colonne de paramètre table.</span><span class="sxs-lookup"><span data-stu-id="a7122-108">SQL_SOPT_SS_NAME_SCOPE should then be set back to the default value, SQL_SS_NAME_SCOPE_TABLE, when the application has finished retrieving table-valued parameter column metadata.</span></span>  
  
 <span data-ttu-id="a7122-109">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME et SQL_CA_SS_SCHEMA_NAME peuvent également être utilisés avec des paramètres de type CLR défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a7122-109">SQL_CA_SS_TYPE_NAME , SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME can also be used with CLR user-defined type parameters.</span></span>  
  
 <span data-ttu-id="a7122-110">Vous ne pouvez pas obtenir les métadonnées de paramètre table pour les instructions préparées qui ne sont pas des appels de procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a7122-110">You cannot obtain table-valued parameter metadata for prepared statements that are not stored procedure calls.</span></span> <span data-ttu-id="a7122-111">Si vous essayez, l'application retourne SQL_ERROR avec SQLSTATE 42000 et le message indiquant une erreur de syntaxe ou une violation d'accès.</span><span class="sxs-lookup"><span data-stu-id="a7122-111">If you try to do this, the application returns SQL_ERROR with SQLSTATE 42000 and the message "Syntax error or access violation".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7122-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7122-112">See Also</span></span>  
 [<span data-ttu-id="a7122-113">Paramètres table &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a7122-113">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
