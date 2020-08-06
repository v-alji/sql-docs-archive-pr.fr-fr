---
title: Création d’index SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- CreateIndex function
- constraints [OLE DB]
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
- adding indexes
ms.assetid: 6239d440-2818-4b98-bb79-732dced41952
author: rothja
ms.author: jroth
ms.openlocfilehash: 3693355eec7a290c03658c10db500161aa52062d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707432"
---
# <a name="creating-sql-server-indexes"></a><span data-ttu-id="5e93b-102">Création d'index SQL Server</span><span class="sxs-lookup"><span data-stu-id="5e93b-102">Creating SQL Server Indexes</span></span>
  <span data-ttu-id="5e93b-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client expose la fonction **IIndexDefinition :: CreateIndex** , ce qui permet aux consommateurs de définir de nouveaux index sur des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span><span class="sxs-lookup"><span data-stu-id="5e93b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::CreateIndex** function, allowing consumers to define new indexes on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="5e93b-104">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client crée des index de table comme des index ou des contraintes.</span><span class="sxs-lookup"><span data-stu-id="5e93b-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates table indexes as either indexes or constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e93b-105">donne le privilège de création de contraintes au propriétaire de la table, au propriétaire de la base de données et aux membres de certains rôles d'administration.</span><span class="sxs-lookup"><span data-stu-id="5e93b-105">gives constraint-creation privilege to the table owner, database owner, and members of certain administrative roles.</span></span> <span data-ttu-id="5e93b-106">Par défaut, seul le propriétaire de la table peut créer un index sur une table.</span><span class="sxs-lookup"><span data-stu-id="5e93b-106">By default, only the table owner can create an index on a table.</span></span> <span data-ttu-id="5e93b-107">Par conséquent, le succès ou l’échec de **CreateIndex** ne dépend pas uniquement des droits d’accès de l’utilisateur de l’application, mais également du type d’index créé.</span><span class="sxs-lookup"><span data-stu-id="5e93b-107">Therefore, the success or failure of **CreateIndex** depends not only on the application user's access rights but also on the type of index created.</span></span>  
  
 <span data-ttu-id="5e93b-108">Les consommateurs spécifient le nom de table en tant que chaîne de caractères Unicode dans le membre *pwszName* de l’union *uName* dans le paramètre *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="5e93b-108">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="5e93b-109">Le membre *eKind* de *pTableID* doit être DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="5e93b-109">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="5e93b-110">Le paramètre *pIndexID* peut avoir la valeur null et, si tel est le cas, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client crée un nom unique pour l’index.</span><span class="sxs-lookup"><span data-stu-id="5e93b-110">The *pIndexID* parameter can be NULL, and if it is, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates a unique name for the index.</span></span> <span data-ttu-id="5e93b-111">Le consommateur peut capturer le nom de l’index en spécifiant un pointeur valide vers un DBID dans le paramètre *ppIndexID*.</span><span class="sxs-lookup"><span data-stu-id="5e93b-111">The consumer can capture the name of the index by specifying a valid pointer to a DBID in the *ppIndexID* parameter.</span></span>  
  
 <span data-ttu-id="5e93b-112">Le consommateur peut spécifier le nom d’index comme chaîne de caractères Unicode dans le membre *pwszName* de l’union *uName* du paramètre *pIndexID*.</span><span class="sxs-lookup"><span data-stu-id="5e93b-112">The consumer can specify the index name as a Unicode character string in the *pwszName* member of the *uName* union of the *pIndexID* parameter.</span></span> <span data-ttu-id="5e93b-113">Le membre *eKind* de *pIndexID* doit être DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="5e93b-113">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="5e93b-114">Le consommateur spécifie la colonne ou les colonnes qui participent à l'index par leur nom.</span><span class="sxs-lookup"><span data-stu-id="5e93b-114">The consumer specifies the column or columns participating in the index by name.</span></span> <span data-ttu-id="5e93b-115">Pour chaque structure DBINDEXCOLUMNDESC utilisée dans **CreateIndex**, le membre *eKind* de *pColumnID* doit être DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="5e93b-115">For each DBINDEXCOLUMNDESC structure used in **CreateIndex**, the *eKind* member of the *pColumnID* must be DBKIND_NAME.</span></span> <span data-ttu-id="5e93b-116">Le nom de la colonne est spécifié comme chaîne de caractères Unicode dans le membre *pwszName*de l’union *uName* de *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="5e93b-116">The name of the column is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *pColumnID*.</span></span>  
  
 <span data-ttu-id="5e93b-117">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prennent en charge l’ordre croissant sur les valeurs de l’index.</span><span class="sxs-lookup"><span data-stu-id="5e93b-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support ascending order on values in the index.</span></span> <span data-ttu-id="5e93b-118">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client retourne E_INVALIDARG si le consommateur spécifie DBINDEX_COL_ORDER_DESC dans une structure DBINDEXCOLUMNDESC.</span><span class="sxs-lookup"><span data-stu-id="5e93b-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns E_INVALIDARG if the consumer specifies DBINDEX_COL_ORDER_DESC in any DBINDEXCOLUMNDESC structure.</span></span>  
  
 <span data-ttu-id="5e93b-119">**CreateIndex** interprète les propriétés d’index de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="5e93b-119">**CreateIndex** interprets index properties as follows.</span></span>  
  
|<span data-ttu-id="5e93b-120">ID de propriété</span><span class="sxs-lookup"><span data-stu-id="5e93b-120">Property ID</span></span>|<span data-ttu-id="5e93b-121">Description</span><span class="sxs-lookup"><span data-stu-id="5e93b-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5e93b-122">DBPROP_INDEX_AUTOUPDATE</span><span class="sxs-lookup"><span data-stu-id="5e93b-122">DBPROP_INDEX_AUTOUPDATE</span></span>|<span data-ttu-id="5e93b-123">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-123">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-124">Valeur par défaut : aucune</span><span class="sxs-lookup"><span data-stu-id="5e93b-124">Default: None</span></span><br /><br /> <span data-ttu-id="5e93b-125">Description : le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ne prend pas en charge cette propriété.</span><span class="sxs-lookup"><span data-stu-id="5e93b-125">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="5e93b-126">Les tentatives de définir la propriété dans **CreateIndex** provoquent une valeur de retour DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="5e93b-126">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="5e93b-127">Le membre *dwStatus* de la structure de propriété indique DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="5e93b-127">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="5e93b-128">DBPROP_INDEX_CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="5e93b-128">DBPROP_INDEX_CLUSTERED</span></span>|<span data-ttu-id="5e93b-129">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-129">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-130">Valeur par défaut : VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="5e93b-130">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="5e93b-131">Description : contrôle le clustering d'index.</span><span class="sxs-lookup"><span data-stu-id="5e93b-131">Description: Controls index clustering.</span></span><br /><br /> <span data-ttu-id="5e93b-132">VARIANT_TRUE : le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client tente de créer un index cluster sur la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span><span class="sxs-lookup"><span data-stu-id="5e93b-132">VARIANT_TRUE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a clustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5e93b-133">prend en charge au plus un index cluster sur une table.</span><span class="sxs-lookup"><span data-stu-id="5e93b-133">supports at most one clustered index on any table.</span></span><br /><br /> <span data-ttu-id="5e93b-134">VARIANT_FALSE : le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client tente de créer un index non-cluster sur la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span><span class="sxs-lookup"><span data-stu-id="5e93b-134">VARIANT_FALSE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a nonclustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|<span data-ttu-id="5e93b-135">DBPROP_INDEX_FILLFACTOR</span><span class="sxs-lookup"><span data-stu-id="5e93b-135">DBPROP_INDEX_FILLFACTOR</span></span>|<span data-ttu-id="5e93b-136">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-136">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-137">Valeur par défaut : 0</span><span class="sxs-lookup"><span data-stu-id="5e93b-137">Default: 0</span></span><br /><br /> <span data-ttu-id="5e93b-138">Description : spécifie le pourcentage d'une page d'index utilisée pour le stockage.</span><span class="sxs-lookup"><span data-stu-id="5e93b-138">Description: Specifies the percentage of an index page used for storage.</span></span> <span data-ttu-id="5e93b-139">Pour plus d’informations, consultez [Create index](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5e93b-139">For more information, see [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span></span><br /><br /> <span data-ttu-id="5e93b-140">Le type de la variante est VT_I4.</span><span class="sxs-lookup"><span data-stu-id="5e93b-140">The type of the variant is VT_I4.</span></span> <span data-ttu-id="5e93b-141">La valeur doit être supérieure ou égale à 1 et inférieure ou égale à 100.</span><span class="sxs-lookup"><span data-stu-id="5e93b-141">The value must be greater than or equal to 1 and less than or equal to 100.</span></span>|  
|<span data-ttu-id="5e93b-142">DBPROP_INDEX_INITIALIZE</span><span class="sxs-lookup"><span data-stu-id="5e93b-142">DBPROP_INDEX_INITIALIZE</span></span>|<span data-ttu-id="5e93b-143">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-143">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-144">Valeur par défaut : aucune</span><span class="sxs-lookup"><span data-stu-id="5e93b-144">Default: None</span></span><br /><br /> <span data-ttu-id="5e93b-145">Description : le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ne prend pas en charge cette propriété.</span><span class="sxs-lookup"><span data-stu-id="5e93b-145">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="5e93b-146">Les tentatives de définir la propriété dans **CreateIndex** provoquent une valeur de retour DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="5e93b-146">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="5e93b-147">Le membre *dwStatus* de la structure de propriété indique DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="5e93b-147">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="5e93b-148">DBPROP_INDEX_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="5e93b-148">DBPROP_INDEX_NULLCOLLATION</span></span>|<span data-ttu-id="5e93b-149">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-149">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-150">Valeur par défaut : aucune</span><span class="sxs-lookup"><span data-stu-id="5e93b-150">Default: None</span></span><br /><br /> <span data-ttu-id="5e93b-151">Description : le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ne prend pas en charge cette propriété.</span><span class="sxs-lookup"><span data-stu-id="5e93b-151">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="5e93b-152">Les tentatives de définir la propriété dans **CreateIndex** provoquent une valeur de retour DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="5e93b-152">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="5e93b-153">Le membre *dwStatus* de la structure de propriété indique DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="5e93b-153">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="5e93b-154">DBPROP_INDEX_NULLS</span><span class="sxs-lookup"><span data-stu-id="5e93b-154">DBPROP_INDEX_NULLS</span></span>|<span data-ttu-id="5e93b-155">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-155">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-156">Valeur par défaut : aucune</span><span class="sxs-lookup"><span data-stu-id="5e93b-156">Default: None</span></span><br /><br /> <span data-ttu-id="5e93b-157">Description : le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ne prend pas en charge cette propriété.</span><span class="sxs-lookup"><span data-stu-id="5e93b-157">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="5e93b-158">Les tentatives de définir la propriété dans **CreateIndex** provoquent une valeur de retour DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="5e93b-158">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="5e93b-159">Le membre *dwStatus* de la structure de propriété indique DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="5e93b-159">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="5e93b-160">DBPROP_INDEX_PRIMARYKEY</span><span class="sxs-lookup"><span data-stu-id="5e93b-160">DBPROP_INDEX_PRIMARYKEY</span></span>|<span data-ttu-id="5e93b-161">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-161">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-162">Valeur par défaut : VARIANT_FALSE Description : crée l'index comme intégrité référentielle, contrainte PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="5e93b-162">Default: VARIANT_FALSE Description: Creates the index as a referential integrity, PRIMARY KEY constraint.</span></span><br /><br /> <span data-ttu-id="5e93b-163">VARIANT_TRUE : l'index est créé pour prendre en charge la contrainte PRIMARY KEY de la table.</span><span class="sxs-lookup"><span data-stu-id="5e93b-163">VARIANT_TRUE: The index is created to support the PRIMARY KEY constraint of the table.</span></span> <span data-ttu-id="5e93b-164">Les colonnes ne doivent pas accepter les valeurs null.</span><span class="sxs-lookup"><span data-stu-id="5e93b-164">The columns must be nonnullable.</span></span><br /><br /> <span data-ttu-id="5e93b-165">VARIANT_FALSE : l'index n'est pas utilisé comme contrainte PRIMARY KEY pour les valeurs de ligne de la table.</span><span class="sxs-lookup"><span data-stu-id="5e93b-165">VARIANT_FALSE: The index is not used as a PRIMARY KEY constraint for row values in the table.</span></span>|  
|<span data-ttu-id="5e93b-166">DBPROP_INDEX_SORTBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="5e93b-166">DBPROP_INDEX_SORTBOOKMARKS</span></span>|<span data-ttu-id="5e93b-167">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-167">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-168">Valeur par défaut : aucune</span><span class="sxs-lookup"><span data-stu-id="5e93b-168">Default: None</span></span><br /><br /> <span data-ttu-id="5e93b-169">Description : le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ne prend pas en charge cette propriété.</span><span class="sxs-lookup"><span data-stu-id="5e93b-169">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="5e93b-170">Les tentatives de définir la propriété dans **CreateIndex** provoquent une valeur de retour DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="5e93b-170">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="5e93b-171">Le membre *dwStatus* de la structure de propriété indique DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="5e93b-171">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="5e93b-172">DBPROP_INDEX_TEMPINDEX</span><span class="sxs-lookup"><span data-stu-id="5e93b-172">DBPROP_INDEX_TEMPINDEX</span></span>|<span data-ttu-id="5e93b-173">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-173">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-174">Valeur par défaut : aucune</span><span class="sxs-lookup"><span data-stu-id="5e93b-174">Default: None</span></span><br /><br /> <span data-ttu-id="5e93b-175">Description : le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ne prend pas en charge cette propriété.</span><span class="sxs-lookup"><span data-stu-id="5e93b-175">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="5e93b-176">Les tentatives de définir la propriété dans **CreateIndex** provoquent une valeur de retour DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="5e93b-176">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="5e93b-177">Le membre *dwStatus* de la structure de propriété indique DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="5e93b-177">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="5e93b-178">DBPROP_INDEX_TYPE</span><span class="sxs-lookup"><span data-stu-id="5e93b-178">DBPROP_INDEX_TYPE</span></span>|<span data-ttu-id="5e93b-179">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-179">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-180">Valeur par défaut : aucune</span><span class="sxs-lookup"><span data-stu-id="5e93b-180">Default: None</span></span><br /><br /> <span data-ttu-id="5e93b-181">Description : le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ne prend pas en charge cette propriété.</span><span class="sxs-lookup"><span data-stu-id="5e93b-181">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="5e93b-182">Les tentatives de définir la propriété dans **CreateIndex** provoquent une valeur de retour DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="5e93b-182">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="5e93b-183">Le membre *dwStatus* de la structure de propriété indique DBPROPSTATUS_BADVALUE.</span><span class="sxs-lookup"><span data-stu-id="5e93b-183">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="5e93b-184">DBPROP_INDEX_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="5e93b-184">DBPROP_INDEX_UNIQUE</span></span>|<span data-ttu-id="5e93b-185">R/W : Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="5e93b-185">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="5e93b-186">Valeur par défaut : VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="5e93b-186">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="5e93b-187">Description : crée l'index comme contrainte UNIQUE sur la colonne ou les colonnes participantes.</span><span class="sxs-lookup"><span data-stu-id="5e93b-187">Description: Creates the index as a UNIQUE constraint on the participating column or columns.</span></span><br /><br /> <span data-ttu-id="5e93b-188">VARIANT_TRUE : l'index est utilisé pour définir une contrainte unique sur les valeurs de ligne de la table.</span><span class="sxs-lookup"><span data-stu-id="5e93b-188">VARIANT_TRUE: The index is used to uniquely constrain row values in the table.</span></span><br /><br /> <span data-ttu-id="5e93b-189">VARIANT_FALSE : l'index ne définit pas de contrainte unique sur les valeurs de ligne.</span><span class="sxs-lookup"><span data-stu-id="5e93b-189">VARIANT_FALSE: The index does not uniquely constrain row values.</span></span>|  
  
 <span data-ttu-id="5e93b-190">Dans le jeu de propriétés spécifiques au fournisseur DBPROPSET_SQLSERVERINDEX, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client définit la propriété d’informations de la source de données suivante.</span><span class="sxs-lookup"><span data-stu-id="5e93b-190">In the provider-specific property set DBPROPSET_SQLSERVERINDEX, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information property.</span></span>  
  
|<span data-ttu-id="5e93b-191">ID de propriété</span><span class="sxs-lookup"><span data-stu-id="5e93b-191">Property ID</span></span>|<span data-ttu-id="5e93b-192">Description</span><span class="sxs-lookup"><span data-stu-id="5e93b-192">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5e93b-193">SSPROP_INDEX_XML</span><span class="sxs-lookup"><span data-stu-id="5e93b-193">SSPROP_INDEX_XML</span></span>|<span data-ttu-id="5e93b-194">Type : VT_BOOL (R/W)</span><span class="sxs-lookup"><span data-stu-id="5e93b-194">Type: VT_BOOL (R/W)</span></span><br /><br /> <span data-ttu-id="5e93b-195">Valeur par défaut : VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="5e93b-195">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="5e93b-196">Description : lorsque cette propriété est spécifiée avec la valeur VARIANT_TRUE avec IIndexDefinition::CreateIndex, il s'ensuit la création d'un index xml primaire, correspondant à la colonne indexée.</span><span class="sxs-lookup"><span data-stu-id="5e93b-196">Description: When this property is specified with a value of VARIANT_TRUE with IIndexDefinition::CreateIndex, it results in a primary xml index being created corresponding to the column being indexed.</span></span> <span data-ttu-id="5e93b-197">Si cette propriété est VARIANT_TRUE, cIndexColumnDescs doit être 1, sinon, il s'agit d'une erreur.</span><span class="sxs-lookup"><span data-stu-id="5e93b-197">If this property is VARIANT_TRUE, cIndexColumnDescs should be 1, otherwise it is an error.</span></span>|  
  
 <span data-ttu-id="5e93b-198">Cet exemple crée un index de clé primaire :</span><span class="sxs-lookup"><span data-stu-id="5e93b-198">This example creates a primary key index:</span></span>  
  
```  
// This CREATE TABLE statement shows the referential integrity and   
// PRIMARY KEY constraint on the OrderDetails table that will be created   
// by the following example code.  
//  
// CREATE TABLE OrderDetails  
// (  
//    OrderID      int      NOT NULL  
//    ProductID   int      NOT NULL  
//        CONSTRAINT PK_OrderDetails  
//        PRIMARY KEY CLUSTERED (OrderID, ProductID),  
//    UnitPrice   money      NOT NULL,  
//    Quantity   int      NOT NULL,  
//    Discount   decimal(2,2)   NOT NULL  
//        DEFAULT 0  
// )  
//  
HRESULT CreatePrimaryKey  
    (  
    IIndexDefinition* pIIndexDefinition  
    )  
    {  
    HRESULT             hr = S_OK;  
  
    DBID                dbidTable;  
    DBID                dbidIndex;  
    const ULONG         nCols = 2;  
    ULONG               nCol;  
    const ULONG         nProps = 2;  
    ULONG               nProp;  
  
    DBINDEXCOLUMNDESC   dbidxcoldesc[nCols];  
    DBPROP              dbpropIndex[nProps];  
    DBPROPSET           dbpropset;  
  
    DBID*               pdbidIndexOut = NULL;  
  
    // Set up identifiers for the table and index.  
    dbidTable.eKind = DBKIND_NAME;  
    dbidTable.uName.pwszName = L"OrderDetails";  
  
    dbidIndex.eKind = DBKIND_NAME;  
    dbidIndex.uName.pwszName = L"PK_OrderDetails";  
  
    // Set up column identifiers.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        dbidxcoldesc[nCol].pColumnID = new DBID;  
        dbidxcoldesc[nCol].pColumnID->eKind = DBKIND_NAME;  
  
        dbidxcoldesc[nCol].eIndexColOrder = DBINDEX_COL_ORDER_ASC;  
        }  
    dbidxcoldesc[0].pColumnID->uName.pwszName = L"OrderID";  
    dbidxcoldesc[1].pColumnID->uName.pwszName = L"ProductID";  
  
    // Set properties for the index. The index is clustered,  
    // PRIMARY KEY.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        dbpropIndex[nProp].dwOptions = DBPROPOPTIONS_REQUIRED;  
        dbpropIndex[nProp].colid = DB_NULLID;  
  
        VariantInit(&(dbpropIndex[nProp].vValue));  
  
        dbpropIndex[nProp].vValue.vt = VT_BOOL;  
        }  
    dbpropIndex[0].dwPropertyID = DBPROP_INDEX_CLUSTERED;  
    dbpropIndex[0].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropIndex[1].dwPropertyID = DBPROP_INDEX_PRIMARYKEY;  
    dbpropIndex[1].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropset.rgProperties = dbpropIndex;  
    dbpropset.cProperties = nProps;  
    dbpropset.guidPropertySet = DBPROPSET_INDEX;  
  
    hr = pIIndexDefinition->CreateIndex(&dbidTable, &dbidIndex, nCols,  
        dbidxcoldesc, 1, &dbpropset, &pdbidIndexOut);  
  
    // Clean up dynamically allocated DBIDs.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        delete dbidxcoldesc[nCol].pColumnID;  
        }  
  
    return (hr);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e93b-199">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e93b-199">See Also</span></span>  
 [<span data-ttu-id="5e93b-200">Tables et index</span><span class="sxs-lookup"><span data-stu-id="5e93b-200">Tables and Indexes</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
  
