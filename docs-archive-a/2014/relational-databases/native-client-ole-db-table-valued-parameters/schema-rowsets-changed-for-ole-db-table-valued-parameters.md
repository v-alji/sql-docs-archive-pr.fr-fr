---
title: Ensembles de lignes de schéma modifiés pour les paramètres table OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- schema rowsets [OLE DB]
- table-valued parameters (OLE DB), schema rowsets changed for (OLE DB)
ms.assetid: 581e3ead-53db-44da-8718-f3fc4b5108f1
author: rothja
ms.author: jroth
ms.openlocfilehash: e09d5127f332c8b6cc948be3eeb74e600bb856f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707440"
---
# <a name="schema-rowsets-changed-for-ole-db-table-valued-parameters"></a><span data-ttu-id="7a6fa-102">Ensembles de lignes de schéma modifiés pour les paramètres table OLE DB</span><span class="sxs-lookup"><span data-stu-id="7a6fa-102">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>
  <span data-ttu-id="7a6fa-103">Le tableau suivant répertorie les ensembles de lignes de schéma qui ont été modifiés ou ajoutés pour prendre en charge des paramètres table.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-103">The following are the schema rowsets that have been changed or added to support table-valued parameters.</span></span>  
  
|<span data-ttu-id="7a6fa-104">Ensemble de lignes de schéma</span><span class="sxs-lookup"><span data-stu-id="7a6fa-104">Schema rowset</span></span>|<span data-ttu-id="7a6fa-105">Description</span><span class="sxs-lookup"><span data-stu-id="7a6fa-105">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="7a6fa-106">DBSCHEMA_PROCEDURE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7a6fa-106">DBSCHEMA_PROCEDURE_PARAMETERS</span></span>|<span data-ttu-id="7a6fa-107">Deux nouvelles colonnes ont été ajoutées à la fin de l'ensemble de lignes nommé SS_TYPE_CATALOG_NAME et SS_TYPE_SCHEMANAME.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-107">Two new columns were added at the end of the rowset named SS_TYPE_CATALOG_NAME and SS_TYPE_SCHEMANAME.</span></span> <span data-ttu-id="7a6fa-108">Ces colonnes peuvent être réutilisées pour des types futurs.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-108">These columns could be re-used for future types.</span></span> <span data-ttu-id="7a6fa-109">Les colonnes TYPE_NAME et LOCAL_TYPE_NAME contiendront le nom du type TABLE de paramètre table.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-109">The TYPE_NAME and LOCAL_TYPE_NAME columns will contain the name of the table-valued parameter TABLE type.</span></span> <span data-ttu-id="7a6fa-110">La colonne DATA_TYPE aura la valeur DBTYPE_TABLE = 143 pour les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-110">The DATA_TYPE column will have value DBTYPE_TABLE = 143 for table-valued parameters.</span></span>|  
|<span data-ttu-id="7a6fa-111">DBSCHEMA_TABLE_TYPES</span><span class="sxs-lookup"><span data-stu-id="7a6fa-111">DBSCHEMA_TABLE_TYPES</span></span>|<span data-ttu-id="7a6fa-112">Cet ensemble de lignes a été ajouté pour prendre en charge des paramètres table.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-112">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="7a6fa-113">Il est identique à DBSCHEMA_TABLES, à la différence près qu'il retourne uniquement des métadonnées pour des types de table plutôt que pour des tables, des vues ou des synonymes.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-113">It is identical to DBSCHEMA_TABLES, except that it returns metadata only for table types, rather than for tables, views, or synonyms.</span></span> <span data-ttu-id="7a6fa-114">La colonne TABLE_TYPE aura la valeur « TABLE TYPE ».</span><span class="sxs-lookup"><span data-stu-id="7a6fa-114">The TABLE_TYPE column will have the value 'TABLE TYPE'.</span></span>|  
|<span data-ttu-id="7a6fa-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="7a6fa-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span></span>|<span data-ttu-id="7a6fa-116">Cet ensemble de lignes a été ajouté pour prendre en charge des paramètres table.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-116">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="7a6fa-117">Il est identique à DBSCHEMA_PRIMARY_KEYS, à la différence près qu'il retourne uniquement des métadonnées de clés primaires pour des types de table plutôt que pour des tables.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-117">It is identical to DBSCHEMA_PRIMARY_KEYS, except that it returns primary keys metadata only for table types, rather than for tables.</span></span>|  
|<span data-ttu-id="7a6fa-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="7a6fa-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span></span>|<span data-ttu-id="7a6fa-119">Cet ensemble de lignes a été ajouté pour prendre en charge des paramètres table.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-119">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="7a6fa-120">Il est identique à DBSCHEMA_COLUMNS, à la différence près qu'il retourne uniquement des métadonnées de colonne pour des types de table plutôt que pour des tables, des vues ou des synonymes.</span><span class="sxs-lookup"><span data-stu-id="7a6fa-120">It is identical to DBSCHEMA_COLUMNS, except that it returns column metadata only for table types, rather than for tables, views, or synonyms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a6fa-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a6fa-121">See Also</span></span>  
 <span data-ttu-id="7a6fa-122">[Paramètres table &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="7a6fa-122">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="7a6fa-123">Utiliser les paramètres table &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="7a6fa-123">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
