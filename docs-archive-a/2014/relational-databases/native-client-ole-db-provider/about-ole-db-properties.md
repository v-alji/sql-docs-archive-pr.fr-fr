---
title: À propos des propriétés OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, properties
- SQL Server Native Client OLE DB provider, properties
- properties [OLE DB]
- property values [SQL Server Native Client]
ms.assetid: 0b36a61e-b542-400d-a3d2-e6f643caf2c6
author: rothja
ms.author: jroth
ms.openlocfilehash: d4eb80ab9c0ab90da11d8580e9a2983455b676bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698130"
---
# <a name="about-ole-db-properties"></a><span data-ttu-id="91a58-102">À propos des propriétés OLE DB</span><span class="sxs-lookup"><span data-stu-id="91a58-102">About OLE DB Properties</span></span>
  <span data-ttu-id="91a58-103">Les consommateurs définissent des valeurs de propriétés afin de demander un comportement d'objet spécifique.</span><span class="sxs-lookup"><span data-stu-id="91a58-103">Consumers set property values to request specific object behavior.</span></span> <span data-ttu-id="91a58-104">Par exemple, ils utilisent des propriétés pour spécifier les interfaces à exposer par un ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="91a58-104">For example, consumers use properties to specify the interfaces to be exposed by a rowset.</span></span> <span data-ttu-id="91a58-105">Ils obtiennent les valeurs de propriétés afin de déterminer les capacités d'un objet, tel qu'un ensemble de lignes, une session ou un objet source de données.</span><span class="sxs-lookup"><span data-stu-id="91a58-105">Consumers get the property values to determine the capabilities of an object, such as a rowset, a session, or a data source object.</span></span>  
  
 <span data-ttu-id="91a58-106">Chaque propriété a une valeur, un type, une description et un attribut de lecture/écriture et, pour les propriétés d'ensemble de lignes, un indicateur signalant s'il peut être appliqué sur la base de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="91a58-106">Each property has a value, type, description, and read/write attribute, and for rowset properties, an indicator of whether it can be applied on a column-by-column basis.</span></span>  
  
 <span data-ttu-id="91a58-107">Une propriété est identifiée par un GUID et un entier représentant l'ID de propriété.</span><span class="sxs-lookup"><span data-stu-id="91a58-107">A property is identified by a GUID and an integer representing the property ID.</span></span> <span data-ttu-id="91a58-108">Un jeu de propriétés est un jeu de toutes les propriétés qui partagent le même GUID.</span><span class="sxs-lookup"><span data-stu-id="91a58-108">A property set is a set of all properties that share the same GUID.</span></span> <span data-ttu-id="91a58-109">Outre les jeux de propriétés OLE DB prédéfinis, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client implémente des jeux de propriétés et des propriétés spécifiques au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="91a58-109">In addition to the predefined OLE DB property sets, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements provider-specific property sets and properties in them.</span></span> <span data-ttu-id="91a58-110">Chaque propriété appartient à un ou plusieurs groupes de propriétés.</span><span class="sxs-lookup"><span data-stu-id="91a58-110">Each property belongs to one or more property groups.</span></span> <span data-ttu-id="91a58-111">Un groupe de propriétés est le groupe de toutes les propriétés qui s'appliquent à un objet particulier.</span><span class="sxs-lookup"><span data-stu-id="91a58-111">A property group is the group of all properties that apply to a particular object.</span></span> <span data-ttu-id="91a58-112">Parmi les groupes de propriétés, on peut citer le groupe de propriétés d'initialisation, le groupe de propriétés de source de données, le groupe de propriétés de session, le groupe de propriétés d'ensemble de lignes, le groupe de propriétés de table et le groupe des propriétés de colonnes.</span><span class="sxs-lookup"><span data-stu-id="91a58-112">Some property groups include the initialization property group, data source property group, session property group, rowset property group, table property group, and column property group.</span></span> <span data-ttu-id="91a58-113">Il y a des propriétés dans chacun de ces groupes de propriétés.</span><span class="sxs-lookup"><span data-stu-id="91a58-113">There are properties in each of these property groups.</span></span>  
  
 <span data-ttu-id="91a58-114">La définition de valeurs de propriétés implique les opérations suivantes</span><span class="sxs-lookup"><span data-stu-id="91a58-114">Setting property values involves:</span></span>  
  
1.  <span data-ttu-id="91a58-115">Détermination des propriétés pour lesquelles il faut définir des valeurs.</span><span class="sxs-lookup"><span data-stu-id="91a58-115">Determining the properties for which to set values.</span></span>  
  
2.  <span data-ttu-id="91a58-116">Détermination des jeux de propriétés qui contiennent les propriétés identifiées.</span><span class="sxs-lookup"><span data-stu-id="91a58-116">Determining the property sets that contain the identified properties.</span></span>  
  
3.  <span data-ttu-id="91a58-117">Allocation d'un tableau de structures DBPROPSET, une pour chaque jeu de propriétés identifié.</span><span class="sxs-lookup"><span data-stu-id="91a58-117">Allocating an array of DBPROPSET structures, one for each identified property set.</span></span>  
  
4.  <span data-ttu-id="91a58-118">Allocation d'un tableau de structures DBPROP pour chaque jeu de propriétés.</span><span class="sxs-lookup"><span data-stu-id="91a58-118">Allocating an array of DBPROP structures for each property set.</span></span> <span data-ttu-id="91a58-119">Le nombre d'éléments dans chaque tableau est le nombre de propriétés (identifiées à l'Étape 1) qui appartiennent à ce jeu de propriétés.</span><span class="sxs-lookup"><span data-stu-id="91a58-119">The number of elements in each array is the number of properties (identified in Step 1) that belong to that property set.</span></span>  
  
5.  <span data-ttu-id="91a58-120">Remplissage de la structure DBPROP pour chaque propriété.</span><span class="sxs-lookup"><span data-stu-id="91a58-120">Filling in the DBPROP structure for each property.</span></span>  
  
6.  <span data-ttu-id="91a58-121">Remplissage des informations (GUID de jeu de propriétés, nombre d'éléments et un pointeur vers le tableau DBPROP correspondant) dans la structure DBPROPSET pour chaque jeu de propriétés.</span><span class="sxs-lookup"><span data-stu-id="91a58-121">Filling in information (property set GUID, count of number of elements, and a pointer to the corresponding DBPROP array) in the DBPROPSET structure for each property set.</span></span>  
  
7.  <span data-ttu-id="91a58-122">Appel d'une méthode pour définir des propriétés et passer le nombre et le tableau de structures DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="91a58-122">Calling a method to set properties and passing the count and the array of DBPROPSET structures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a58-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="91a58-123">See Also</span></span>  
 <span data-ttu-id="91a58-124">[Création d’une application SQL Server Native Client OLE DB Provider](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="91a58-124">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="91a58-125">Propriétés (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="91a58-125">Properties (OLE DB)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112207)  
  
  
