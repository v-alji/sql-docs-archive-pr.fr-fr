---
title: Gestionnaire de connexions du cache | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Cache connection manager
ms.assetid: bdc92038-3720-4795-8a5c-79b963f2c952
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b8a7cc8bbe9e93c385fca6257e0be2e79bd3148a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605665"
---
# <a name="cache-connection-manager"></a><span data-ttu-id="329c3-102">Gestionnaire de connexions du cache</span><span class="sxs-lookup"><span data-stu-id="329c3-102">Cache Connection Manager</span></span>
  <span data-ttu-id="329c3-103">Le gestionnaire de connexions du cache lit des données à partir de la transformation du cache ou d'un fichier cache (.caw) et peut enregistrer les données dans un fichier cache.</span><span class="sxs-lookup"><span data-stu-id="329c3-103">The Cache connection manager reads data from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="329c3-104">Les données sont toujours stockées en mémoire que vous configuriez ou non le gestionnaire de connexions du cache pour utiliser un fichier cache.</span><span class="sxs-lookup"><span data-stu-id="329c3-104">Whether you configure the Cache connection manager to use a cache file, the data is always stored in memory.</span></span>  
  
 <span data-ttu-id="329c3-105">La transformation du cache écrit des données provenant d'une source de données connectée dans le flux de données dans un gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="329c3-105">The Cache Transform transformation writes data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="329c3-106">La transformation de recherche dans un package effectue des recherches sur les données.</span><span class="sxs-lookup"><span data-stu-id="329c3-106">The Lookup transformation in a package performs lookups on the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="329c3-107">Le gestionnaire de connexions du cache ne prend pas en charge les types de données de l'objet BLOB (Binary Large Object) DT_TEXT, DT_NTEXT et DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="329c3-107">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="329c3-108">Si le dataset de référence contient un type de données d'objet BLOB, le composant échoue lorsque vous exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="329c3-108">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="329c3-109">Vous pouvez utiliser l' **Éditeur du gestionnaire de connexions du cache** pour modifier des types de données de colonne.</span><span class="sxs-lookup"><span data-stu-id="329c3-109">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span> <span data-ttu-id="329c3-110">Pour plus d’informations, consultez [Éditeur du gestionnaire de connexions du cache](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="329c3-110">For more information, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="329c3-111">Le niveau de protection du package ne s'applique pas au fichier cache.</span><span class="sxs-lookup"><span data-stu-id="329c3-111">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="329c3-112">Si le fichier cache contient des informations sensibles, utilisez une liste de contrôle d'accès (ACL) pour restreindre l'accès à l'emplacement ou au dossier dans lequel vous stockez le fichier.</span><span class="sxs-lookup"><span data-stu-id="329c3-112">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="329c3-113">Vous devez autoriser l'accès à certains comptes uniquement.</span><span class="sxs-lookup"><span data-stu-id="329c3-113">You should enable access only to certain accounts.</span></span> <span data-ttu-id="329c3-114">Pour plus d’informations, consultez [Accéder aux fichiers utilisés par des packages](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="329c3-114">For more information, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
## <a name="configuration-of-the-cache-connection-manager"></a><span data-ttu-id="329c3-115">Configuration du gestionnaire de connexions du cache</span><span class="sxs-lookup"><span data-stu-id="329c3-115">Configuration of the Cache Connection Manager</span></span>  
 <span data-ttu-id="329c3-116">Vous pouvez configurer le gestionnaire de connexions du cache comme suit :</span><span class="sxs-lookup"><span data-stu-id="329c3-116">You can configure the Cache connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="329c3-117">Indiquez s'il faut utiliser ou non un fichier cache.</span><span class="sxs-lookup"><span data-stu-id="329c3-117">Indicate whether to use a cache file.</span></span>  
  
     <span data-ttu-id="329c3-118">Si vous configurez le gestionnaire de connexions du cache pour utiliser un fichier cache, il effectuera l'une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="329c3-118">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
    -   <span data-ttu-id="329c3-119">Il enregistrera les données dans le fichier lorsqu'une transformation du cache est configurée pour écrire des données depuis une source de données dans le flux de données dans le gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="329c3-119">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span>  
  
    -   <span data-ttu-id="329c3-120">Il lira des données à partir du fichier cache.</span><span class="sxs-lookup"><span data-stu-id="329c3-120">Read data from the cache file.</span></span>  
  
     <span data-ttu-id="329c3-121">Pour plus d'informations, consultez [Cache Transform](../data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="329c3-121">For more information, see [Cache Transform](../data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="329c3-122">Modifiez les métadonnées des colonnes stockées dans le cache.</span><span class="sxs-lookup"><span data-stu-id="329c3-122">Change metadata for the columns stored in the cache.</span></span>  
  
-   <span data-ttu-id="329c3-123">Mettez à jour le nom du fichier cache au moment de l’exécution en utilisant une expression pour définir la propriété ConnectionString.</span><span class="sxs-lookup"><span data-stu-id="329c3-123">Update the cache file name at runtime by using an expression to set the ConnectionString property.</span></span> <span data-ttu-id="329c3-124">Pour plus d’informations, consultez [Expressions de propriété dans des packages](../expressions/use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="329c3-124">For more information, see [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md).</span></span>  
  
 <span data-ttu-id="329c3-125">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="329c3-125">You can set properties through [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="329c3-126">Pour plus d’informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , consultez [Éditeur du gestionnaire de connexions du cache](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="329c3-126">For more information about the properties that you can set in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="329c3-127">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programmation](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="329c3-127">For information about how to configure a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="329c3-128">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="329c3-128">Related Tasks</span></span>  
 [<span data-ttu-id="329c3-129">Implémenter une transformation de recherche en mode Cache complet à l'aide du gestionnaire de connexions du cache</span><span class="sxs-lookup"><span data-stu-id="329c3-129">Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager</span></span>](lookup-transformation-full-cache-mode-ole-db-connection-manager.md)  
  
  
