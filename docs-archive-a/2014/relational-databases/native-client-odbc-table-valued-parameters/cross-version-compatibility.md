---
title: Compatibilité entre les versions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), cross-version compatibility
ms.assetid: 5f14850b-b85c-41e2-8116-6f5b3f5e0856
author: rothja
ms.author: jroth
ms.openlocfilehash: af434713946f5c568ee71644a7403f9496a8c16f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612812"
---
# <a name="cross-version-compatibility"></a><span data-ttu-id="c88cb-102">Compatibilité des versions</span><span class="sxs-lookup"><span data-stu-id="c88cb-102">Cross-Version Compatibility</span></span>
  <span data-ttu-id="c88cb-103">Les conflits de version peuvent se produire lorsque les instances client ou serveur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieures à [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] sont censées traiter les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="c88cb-103">Cross-version conflicts can occur when client or server instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] are expected to process table-valued parameters.</span></span>  
  
 <span data-ttu-id="c88cb-104">En général, les fonctionnalités des paramètres table ne sont accessibles qu'aux clients [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (avec SQL Server Native Client 10.0) ou version ultérieure connectés aux serveurs [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (ou version ultérieure).</span><span class="sxs-lookup"><span data-stu-id="c88cb-104">In general, table-valued parameter functionality is only available to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] clients (using SQL Server Native Client 10.0) or later that are connected to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) servers.</span></span> <span data-ttu-id="c88cb-105">Les nouvelles colonnes des jeux de résultats de la fonction catalogue ne sont présentes qu’en cas de connexion à un [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] serveur (ou version ultérieure).</span><span class="sxs-lookup"><span data-stu-id="c88cb-105">New columns in catalog function result sets will only be present when connected to a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) server.</span></span>  
  
 <span data-ttu-id="c88cb-106">Si une application cliente compilée avec une version antérieure de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client exécute des instructions qui attendent des paramètres table, le serveur détecte cette situation via une erreur de conversion de données, et ODBC retourne celle-ci comme SQLSTATE 07006, avec le message « Violation de l'attribut de type de données restreint ».</span><span class="sxs-lookup"><span data-stu-id="c88cb-106">If a client application compiled with an earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client executes statements that expect table-valued parameters, the server detects this condition through a data conversion error, and ODBC returns this as a SQLSTATE 07006 and the message "Restricted data type attribute violation".</span></span>  
  
 <span data-ttu-id="c88cb-107">Si une application cliente qui a été compilée avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client 10,0 ou une version ultérieure tente d’utiliser des paramètres table quand elle est connectée à une instance de serveur antérieure à [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client détecte cela, et les appels SQLBindCol, SQLBindParameter, SQLSetDescFields et SQLSetDescRec échouent avec SQLSTATE 07006 et le message «violation de l’attribut de type de données restreint (la version de SQL Server pour cette connexion ne prend</span><span class="sxs-lookup"><span data-stu-id="c88cb-107">If a client application that was compiled with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 or later tries to use table-valued parameters when connected to a server instance earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will detect this, and SQLBindCol, SQLBindParameter, SQLSetDescFields, and SQLSetDescRec calls will fail with SQLSTATE 07006 and the message "Restricted data type attribute violation (the version of SQL Server for this connection does not support table-valued parameters)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88cb-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c88cb-108">See Also</span></span>  
 [<span data-ttu-id="c88cb-109">Paramètres table &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c88cb-109">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
