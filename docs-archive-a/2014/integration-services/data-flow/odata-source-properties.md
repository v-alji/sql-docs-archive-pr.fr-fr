---
title: Propriétés de la source OData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4fde5bb0-6d78-4ec4-8f0b-67f91c53fe99
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8139f79ed595ca3e6204f96823f6bc95e6fb40df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708500"
---
# <a name="odata-source-properties"></a><span data-ttu-id="c3005-102">Propriétés de la source OData</span><span class="sxs-lookup"><span data-stu-id="c3005-102">OData Source Properties</span></span>
  <span data-ttu-id="c3005-103">Quand vous cliquez avec le bouton droit sur **Source OData** dans le flux de données, puis cliquez sur **Propriétés**, vous voyez les propriétés du composant **Source OData** dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="c3005-103">When you right-click **OData Source** in the data flow and click **Properties**, you will see properties for the **OData Source** component in the **Properties** window.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3005-104">Propriété</span><span class="sxs-lookup"><span data-stu-id="c3005-104">Property</span></span>|<span data-ttu-id="c3005-105">Description</span><span class="sxs-lookup"><span data-stu-id="c3005-105">Description</span></span>|  
|<span data-ttu-id="c3005-106">CollectionName</span><span class="sxs-lookup"><span data-stu-id="c3005-106">CollectionName</span></span>|<span data-ttu-id="c3005-107">Nom de la collection que vous souhaitez à extraire du service OData.</span><span class="sxs-lookup"><span data-stu-id="c3005-107">Name of the collection you wish to retrieve from the OData service.</span></span> <span data-ttu-id="c3005-108">La propriété **CollectionName** est utilisée quand **UseResourcePath** a la valeur false.</span><span class="sxs-lookup"><span data-stu-id="c3005-108">The **CollectionName** property is used when **UseResourcePath** is False.</span></span><br /><br /> <span data-ttu-id="c3005-109">Cette propriété utilise des expressions et permet de définir la valeur au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="c3005-109">This property is expression-able, allowing the value to be set at runtime.</span></span> <span data-ttu-id="c3005-110">Cependant, si les métadonnées de la collection ne correspondent pas aux métadonnées utilisées au moment de la conception, une erreur de validation est générée, et l'exécution du flux de données échouera.</span><span class="sxs-lookup"><span data-stu-id="c3005-110">However, if the metadata of the collection does not match the metadata that was used at design time, a validation error will occur, causing the data flow execution to fail.</span></span>|  
|<span data-ttu-id="c3005-111">DefaultStringLength</span><span class="sxs-lookup"><span data-stu-id="c3005-111">DefaultStringLength</span></span>|<span data-ttu-id="c3005-112">Cette valeur spécifie la longueur par défaut des colonnes de chaîne qui n'ont pas de longueur maximale.</span><span class="sxs-lookup"><span data-stu-id="c3005-112">This value specifies default length for string columns that have no max length.</span></span><br /><br /> <span data-ttu-id="c3005-113">**Valeur par défaut :** 4000</span><span class="sxs-lookup"><span data-stu-id="c3005-113">**Default:** 4000</span></span>|  
|<span data-ttu-id="c3005-114">Query</span><span class="sxs-lookup"><span data-stu-id="c3005-114">Query</span></span>|<span data-ttu-id="c3005-115">Paramètres de requête OData.</span><span class="sxs-lookup"><span data-stu-id="c3005-115">The OData query parameters.</span></span> <span data-ttu-id="c3005-116">Cette propriété utilise des expressions et peut être définie au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="c3005-116">This property is expression-able and can be set at runtime.</span></span>|  
|<span data-ttu-id="c3005-117">ResourcePath</span><span class="sxs-lookup"><span data-stu-id="c3005-117">ResourcePath</span></span>|<span data-ttu-id="c3005-118">Utilisez cette propriété lorsque vous devez spécifier un chemin d'accès de ressources complet, plutôt que sélectionner uniquement un nom de collection.</span><span class="sxs-lookup"><span data-stu-id="c3005-118">Use this property when you need to specify a full resource path, rather than just selecting a collection name.</span></span> <span data-ttu-id="c3005-119">Cette propriété est utilisée lorsque **UseResourcePath** a la valeur True.</span><span class="sxs-lookup"><span data-stu-id="c3005-119">This property is used when **UseResourcePath** is True.</span></span>|  
|<span data-ttu-id="c3005-120">UseResourcePath</span><span class="sxs-lookup"><span data-stu-id="c3005-120">UseResourcePath</span></span>|<span data-ttu-id="c3005-121">Lorsque la valeur est définie à True, la valeur **ResourcePath** est ajoutée à l'URL de base pour déterminer l'emplacement du flux OData.</span><span class="sxs-lookup"><span data-stu-id="c3005-121">When set to True, the **ResourcePath** value is appended to the base URL to determine the OData feed location.</span></span> <span data-ttu-id="c3005-122">Lorsque la valeur est False, la valeur **CollectionName** est utilisée.</span><span class="sxs-lookup"><span data-stu-id="c3005-122">When set to False, the **CollectionName** value is used.</span></span><br /><br /> <span data-ttu-id="c3005-123">**Par défaut :** Fausses</span><span class="sxs-lookup"><span data-stu-id="c3005-123">**Default:** False</span></span>|  
  
  
