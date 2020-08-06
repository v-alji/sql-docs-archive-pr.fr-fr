---
title: Transformation du cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetrans.f1
helpviewer_keywords:
- Cache transform
ms.assetid: a5683fc8-9c32-4634-819e-e9815627e4f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34be3252a3caf344c95e13ae45cc485a8c4ffdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611201"
---
# <a name="cache-transform"></a><span data-ttu-id="2f12a-102">Transformation du cache</span><span class="sxs-lookup"><span data-stu-id="2f12a-102">Cache Transform</span></span>
  <span data-ttu-id="2f12a-103">La transformation du cache génère un dataset de référence pour la transformation de recherche en entrant des données depuis une source de données connectée dans le flux de données dans un gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="2f12a-103">The Cache Transform transformation generates a reference dataset for the Lookup Transformation by writing data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="2f12a-104">La transformation de recherche effectue des recherches en joignant les données des colonnes d'entrée d'une source de données connectée aux colonnes de la base de données de référence.</span><span class="sxs-lookup"><span data-stu-id="2f12a-104">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference database.</span></span>  
  
 <span data-ttu-id="2f12a-105">Vous pouvez utiliser le gestionnaire de connexions du cache lorsque vous souhaitez configurer la transformation de recherche en mode cache complet.</span><span class="sxs-lookup"><span data-stu-id="2f12a-105">You can use the Cache connection manager when you want to configure the Lookup Transformation to run in the full cache mode.</span></span> <span data-ttu-id="2f12a-106">Dans ce mode, le dataset de référence est chargé dans le cache avant l'exécution de la transformation de recherche.</span><span class="sxs-lookup"><span data-stu-id="2f12a-106">In this mode, the reference dataset is loaded into cache before the Lookup Transformation runs.</span></span>  
  
 <span data-ttu-id="2f12a-107">Pour savoir comment configurer la transformation de recherche en mode cache complet à l’aide du gestionnaire de connexions du cache et de la transformation du cache, consultez [Implémenter une transformation de recherche en mode Cache complet à l’aide du gestionnaire de connexions du cache](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2f12a-107">For instructions on how to configure the Lookup transformation in full cache mode with the Cache connection manager and Cache Transform transformation, see [Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="2f12a-108">Pour plus d'informations sur la mise en cache du dataset de référence, consultez [Lookup Transformation](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="2f12a-108">For more information on caching the reference dataset, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f12a-109">La transformation du cache écrit uniquement des lignes uniques dans le gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="2f12a-109">The Cache Transform writes only unique rows to the Cache connection manager.</span></span>  
  
 <span data-ttu-id="2f12a-110">Dans un package unique, une seule transformation du cache peut écrire des données dans le même gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="2f12a-110">In a single package, only one Cache Transform can write data to the same Cache connection manager.</span></span> <span data-ttu-id="2f12a-111">Si le package contient plusieurs transformations du cache, la première qui est appelée lors de l'exécution du package écrit les données dans le gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="2f12a-111">If the package contains multiple Cache Transforms, the first Cache Transform that is called when the package runs, writes the data to the connection manager.</span></span> <span data-ttu-id="2f12a-112">Les opérations d'écriture des transformations du cache suivantes échouent.</span><span class="sxs-lookup"><span data-stu-id="2f12a-112">The write operations of subsequent Cache Transforms fail.</span></span>  
  
 <span data-ttu-id="2f12a-113">Pour plus d'informations, consultez [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) et [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2f12a-113">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
## <a name="configuration-of-the-cache-transform"></a><span data-ttu-id="2f12a-114">Configuration de la transformation du cache</span><span class="sxs-lookup"><span data-stu-id="2f12a-114">Configuration of the Cache Transform</span></span>  
 <span data-ttu-id="2f12a-115">Vous pouvez configurer le gestionnaire de connexions du cache afin d'enregistrer les données dans un fichier cache (.caw).</span><span class="sxs-lookup"><span data-stu-id="2f12a-115">You can configure the Cache connection manager to save the data to a cache file (.caw).</span></span>  
  
 <span data-ttu-id="2f12a-116">Vous pouvez configurer la transformation du cache comme suit :</span><span class="sxs-lookup"><span data-stu-id="2f12a-116">You can configure the Cache Transform in the following ways:</span></span>  
  
-   <span data-ttu-id="2f12a-117">Spécifiez le gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="2f12a-117">Specify the Cache connection manager.</span></span>  
  
-   <span data-ttu-id="2f12a-118">Mappez les colonnes d'entrée dans la transformation du cache aux colonnes de destination dans le gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="2f12a-118">Map the input columns in the Cache Transform to destination columns in the Cache connection manager.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f12a-119">Chaque colonne d'entrée doit être mappée à une colonne de destination et les types de données de colonne doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="2f12a-119">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="2f12a-120">Sinon, le Concepteur [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] affiche un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="2f12a-120">Otherwise, [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
     <span data-ttu-id="2f12a-121">Vous pouvez utiliser l' **Éditeur du gestionnaire de connexions du cache** pour modifier les types de données et les noms de colonne, ainsi que d'autres propriétés de colonne.</span><span class="sxs-lookup"><span data-stu-id="2f12a-121">You can use the **Cache Connection Manager Editor** to modify column data types, names, and other column properties.</span></span>  
  
 <span data-ttu-id="2f12a-122">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f12a-122">You can set properties through [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer.</span></span> <span data-ttu-id="2f12a-123">Pour plus d'informations sur les propriétés que vous pouvez définir dans la boîte de dialogue **Éditeur avancé** , consultez [Transformation Custom Properties](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2f12a-123">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="2f12a-124">Pour plus d’informations sur la façon de définir les propriétés, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="2f12a-124">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f12a-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f12a-125">See Also</span></span>  
 <span data-ttu-id="2f12a-126">[Transformations Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="2f12a-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 [<span data-ttu-id="2f12a-127">Flux de données</span><span class="sxs-lookup"><span data-stu-id="2f12a-127">Data Flow</span></span>](../data-flow.md)  
  
  
