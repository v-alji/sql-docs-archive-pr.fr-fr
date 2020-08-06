---
title: Propriétés des informations de la source de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, data source properties
- properties [OLE DB]
- data source properties [OLE DB]
- information properties [OLE DB]
- OLE DB data source properties [SQL Server Native Client]
ms.assetid: 7fd80e47-5bd9-41e2-a3d3-091a7c8c5f2b
author: rothja
ms.author: jroth
ms.openlocfilehash: c10a4e762bbe3421e720753941f5e0a5702832ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708239"
---
# <a name="data-source-information-properties"></a><span data-ttu-id="d77e6-102">Propriétés des informations de la source de données</span><span class="sxs-lookup"><span data-stu-id="d77e6-102">Data Source Information Properties</span></span>
  <span data-ttu-id="d77e6-103">Dans le jeu de propriétés DBPROPSET_SQLSERVERDATASOURCEINFO spécifique au fournisseur, le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client définit les propriétés des informations de la source de données.</span><span class="sxs-lookup"><span data-stu-id="d77e6-103">In the provider-specific property set DBPROPSET_SQLSERVERDATASOURCEINFO, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information properties.</span></span>  
  
|<span data-ttu-id="d77e6-104">ID de propriété</span><span class="sxs-lookup"><span data-stu-id="d77e6-104">Property ID</span></span>|<span data-ttu-id="d77e6-105">Description</span><span class="sxs-lookup"><span data-stu-id="d77e6-105">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d77e6-106">SSPROP_COLUMNLEVELCOLLATION</span><span class="sxs-lookup"><span data-stu-id="d77e6-106">SSPROP_COLUMNLEVELCOLLATION</span></span>|<span data-ttu-id="d77e6-107">Tapez : VT_BOOL</span><span class="sxs-lookup"><span data-stu-id="d77e6-107">Type: VT_BOOL</span></span><br /><br /> <span data-ttu-id="d77e6-108">R/W : Read (Lecture)</span><span class="sxs-lookup"><span data-stu-id="d77e6-108">R/W: Read</span></span><br /><br /> <span data-ttu-id="d77e6-109">Valeur par défaut : VARIANT_TRUE</span><span class="sxs-lookup"><span data-stu-id="d77e6-109">Default: VARIANT_TRUE</span></span><br /><br /> <span data-ttu-id="d77e6-110">Description : utilisé pour déterminer si le classement des colonnes est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d77e6-110">Description: Used to determine if column collation is supported.</span></span><br /><br /> <span data-ttu-id="d77e6-111">VARIANT_TRUE : le classement au niveau des colonnes est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d77e6-111">VARIANT_TRUE: Column level collation is supported.</span></span><br /><br /> <span data-ttu-id="d77e6-112">VARIANT_FALSE : le classement au niveau des colonnes n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d77e6-112">VARIANT_FALSE: Column level collation is not supported.</span></span>|  
|<span data-ttu-id="d77e6-113">SSPROP_UNICODELCID</span><span class="sxs-lookup"><span data-stu-id="d77e6-113">SSPROP_UNICODELCID</span></span>|<span data-ttu-id="d77e6-114">Type : VT_I4 R/W: Read (Lecture)</span><span class="sxs-lookup"><span data-stu-id="d77e6-114">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="d77e6-115">Description : ID des paramètres régionaux Unicode.</span><span class="sxs-lookup"><span data-stu-id="d77e6-115">Description: Unicode locale ID.</span></span><br /><br /> <span data-ttu-id="d77e6-116">Il s'agit des paramètres régionaux utilisés pour le tri des données Unicode.</span><span class="sxs-lookup"><span data-stu-id="d77e6-116">This is the locale used for Unicode data sorting.</span></span>|  
|<span data-ttu-id="d77e6-117">SSPROP_UNICODECOMPARISONSTYLE</span><span class="sxs-lookup"><span data-stu-id="d77e6-117">SSPROP_UNICODECOMPARISONSTYLE</span></span>|<span data-ttu-id="d77e6-118">Type : VT_I4 R/W: Read (Lecture)</span><span class="sxs-lookup"><span data-stu-id="d77e6-118">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="d77e6-119">Description : style de comparaison Unicode.</span><span class="sxs-lookup"><span data-stu-id="d77e6-119">Description: Unicode comparison style.</span></span><br /><br /> <span data-ttu-id="d77e6-120">Options de tri utilisés pour le tri des données Unicode.</span><span class="sxs-lookup"><span data-stu-id="d77e6-120">The sorting options used for Unicode data sorting.</span></span>|  
  
 <span data-ttu-id="d77e6-121">Dans le jeu de propriétés DBPROPSET_SQLSERVERSTREAM spécifique au fournisseur, le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client définit la propriété supplémentaire suivante.</span><span class="sxs-lookup"><span data-stu-id="d77e6-121">In the provider-specific property set DBPROPSET_SQLSERVERSTREAM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following additional property.</span></span>  
  
|<span data-ttu-id="d77e6-122">ID de propriété</span><span class="sxs-lookup"><span data-stu-id="d77e6-122">Property ID</span></span>|<span data-ttu-id="d77e6-123">Description</span><span class="sxs-lookup"><span data-stu-id="d77e6-123">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d77e6-124">SSPROP_STREAM_XMLROOT</span><span class="sxs-lookup"><span data-stu-id="d77e6-124">SSPROP_STREAM_XMLROOT</span></span>|<span data-ttu-id="d77e6-125">Type : VT_BSTR R/W: Read/Write (Lecture/écriture)</span><span class="sxs-lookup"><span data-stu-id="d77e6-125">Type: VT_BSTR R/W: Read/Write</span></span><br /><br /> <span data-ttu-id="d77e6-126">Description : le résultat d'une requête FOR XML ne peut pas être un document bien formé.</span><span class="sxs-lookup"><span data-stu-id="d77e6-126">Description: The result of a FOR XML query may not be a well-formed document.</span></span> <span data-ttu-id="d77e6-127">Lorsque cette propriété est spécifiée, le résultat d'une requête 'select... for XML' est encapsulée dans la balise racine fournie par la propriété pour retourner un document XML bien formé.</span><span class="sxs-lookup"><span data-stu-id="d77e6-127">When this property is specified, the result of a 'select ... for XML' query is wrapped in the root tag provided by this property to return a well formed XML document.</span></span> <span data-ttu-id="d77e6-128">Si la requête est exécutée dans le navigateur, il se peut que le navigateur affiche les erreurs de l'analyseur lors du chargement du résultat.</span><span class="sxs-lookup"><span data-stu-id="d77e6-128">If the query is executed in the browser it may cause the browser to display parser errors when loading the result.</span></span> <span data-ttu-id="d77e6-129">Pour éviter l'erreur, SQL ISAPI prend en charge le mot clé ROOT.</span><span class="sxs-lookup"><span data-stu-id="d77e6-129">To avoid the error, SQL ISAPI supports the keyword ROOT.</span></span> <span data-ttu-id="d77e6-130">Ce mot clé est mappé avec la propriété SSPROP_STREAM_XMLROOT.</span><span class="sxs-lookup"><span data-stu-id="d77e6-130">This keyword maps to SSPROP_STREAM_XMLROOT property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d77e6-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d77e6-131">See Also</span></span>  
 [<span data-ttu-id="d77e6-132">Objets source de données &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d77e6-132">Data Source Objects &#40;OLE DB&#41;</span></span>](data-source-objects-ole-db.md)  
  
  
