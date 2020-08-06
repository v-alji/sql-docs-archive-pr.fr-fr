---
title: Conversion des données de paramètre table et autres erreurs et avertissements | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), data conversion
- table-valued parameters (ODBC), error messages
ms.assetid: edd45234-59dc-4338-94fc-330e820cc248
author: rothja
ms.author: jroth
ms.openlocfilehash: 45b9ba7f91b54548e096bbe47da6e01ba562f59d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600845"
---
# <a name="table-valued-parameter-data-conversion-and-other-errors-and-warnings"></a><span data-ttu-id="ea08d-102">Conversion des données des paramètres table et autres erreurs et avertissements</span><span class="sxs-lookup"><span data-stu-id="ea08d-102">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>
  <span data-ttu-id="ea08d-103">Les valeurs de colonne de paramètre table peuvent être converties du type de données client en type de données serveur de la même manière que toute autre valeur de colonne ou de paramètre.</span><span class="sxs-lookup"><span data-stu-id="ea08d-103">Table-valued parameter column values can be converted between client and server data types in the same way as other column and parameter values.</span></span> <span data-ttu-id="ea08d-104">Toutefois, dans la mesure où un paramètre table peut contenir plusieurs colonnes et plusieurs lignes, il est important de pouvoir identifier la valeur réelle sur laquelle l'erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="ea08d-104">But because a table-valued parameter can contain multiple columns and multiple rows, it is important to be able to identify the actual value where the error occurred.</span></span>  
  
 <span data-ttu-id="ea08d-105">Lorsqu'une erreur ou un avertissement est détecté dans une colonne de paramètre table, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client génère un enregistrement de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="ea08d-105">When an error or warning is detected in a table-valued parameter column, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will generate a diagnostic record.</span></span> <span data-ttu-id="ea08d-106">Le message d'erreur contient le numéro du paramètre table, accompagné de l'ordinal de colonne et du numéro de ligne.</span><span class="sxs-lookup"><span data-stu-id="ea08d-106">The error message will contain the parameter number of the table-valued parameter, plus the column ordinal and row number.</span></span> <span data-ttu-id="ea08d-107">Une application peut également utiliser les champs de diagnostic SQL_DIAG_SS_TABLE_COLUMN_NUMBER et SQL_DIAG_SS_TABLE_ROW_NUMBER dans des enregistrements de diagnostic pour déterminer quelles valeurs sont associées à des erreurs et des avertissements.</span><span class="sxs-lookup"><span data-stu-id="ea08d-107">An application can also use the diagnostic fields SQL_DIAG_SS_TABLE_COLUMN_NUMBER and SQL_DIAG_SS_TABLE_ROW_NUMBER within diagnostic records to determine which values are associated with errors and warnings.</span></span> <span data-ttu-id="ea08d-108">Ces champs de diagnostic sont disponibles dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="ea08d-108">These diagnostic fields are available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span>  
  
 <span data-ttu-id="ea08d-109">Les composants SQLSTATE et message des enregistrements de diagnostic sont conformes au comportement ODBC existant pour tous les autres aspects.</span><span class="sxs-lookup"><span data-stu-id="ea08d-109">The SQLSTATE and message components of diagnostic records will conform to existing ODBC behavior in all other respects.</span></span> <span data-ttu-id="ea08d-110">Autrement dit, à l’exception des informations d’identification des paramètres, des lignes et des colonnes, les messages d’erreur ont les mêmes valeurs pour les paramètres table que pour les paramètres qui ne sont pas des tables.</span><span class="sxs-lookup"><span data-stu-id="ea08d-110">That is, except for the parameter, row, and column identification information, error messages have the same values for table-valued parameters as they would for non-table-valued parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea08d-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea08d-111">See Also</span></span>  
 [<span data-ttu-id="ea08d-112">Paramètres table &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ea08d-112">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
