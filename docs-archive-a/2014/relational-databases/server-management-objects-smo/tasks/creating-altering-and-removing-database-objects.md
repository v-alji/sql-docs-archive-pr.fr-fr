---
title: Utilisation des objets de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- database objects [SMO]
- objects [SMO]
ms.assetid: 702fd63d-8734-4a02-872e-aecfb037c787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 14dd0c0175a23f809fc925c5104ac15ac408805b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707351"
---
# <a name="working-with-database-objects"></a><span data-ttu-id="166a1-102">Utilisation des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="166a1-102">Working with Database Objects</span></span>
  <span data-ttu-id="166a1-103">Les étapes de la création d'objets SMO sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="166a1-103">The stages of SMO object creation are as follows:</span></span>  
  
1.  <span data-ttu-id="166a1-104">Créer une instance de l'objet.</span><span class="sxs-lookup"><span data-stu-id="166a1-104">Create an instance of the object.</span></span>  
  
2.  <span data-ttu-id="166a1-105">Définir les propriétés de l'objet.</span><span class="sxs-lookup"><span data-stu-id="166a1-105">Set the object properties.</span></span>  
  
3.  <span data-ttu-id="166a1-106">Créer les instances des objets enfants.</span><span class="sxs-lookup"><span data-stu-id="166a1-106">Create instances of the child objects.</span></span>  
  
4.  <span data-ttu-id="166a1-107">Définir les propriétés des objets enfants.</span><span class="sxs-lookup"><span data-stu-id="166a1-107">Set the child object properties.</span></span>  
  
5.  <span data-ttu-id="166a1-108">Créer l'objet.</span><span class="sxs-lookup"><span data-stu-id="166a1-108">Create the object.</span></span>  
  
 <span data-ttu-id="166a1-109">Lorsque les instances d'objets SMO sont créées dans une application SMO, ils n'existent pas sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], jusqu'à ce que la méthode `Create` soit émise.</span><span class="sxs-lookup"><span data-stu-id="166a1-109">When instances of SMO objects are created in an SMO application, they do not exist on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] until the `Create` method is issued.</span></span> <span data-ttu-id="166a1-110">Toutefois, il n'est pas nécessaire d'émettre une méthode `Create` pour chaque objet individuel.</span><span class="sxs-lookup"><span data-stu-id="166a1-110">However, it is not necessary to issue a `Create` method for every individual object.</span></span> <span data-ttu-id="166a1-111">Si un objet possède un jeu d'objets enfants, seul l'objet parent est requis pour exécuter la méthode `Create`.</span><span class="sxs-lookup"><span data-stu-id="166a1-111">If an object has a set of child objects, only the parent object is required to run the `Create` method.</span></span> <span data-ttu-id="166a1-112">Par exemple, la définition d'une table nécessite qu'elle contienne au moins une colonne.</span><span class="sxs-lookup"><span data-stu-id="166a1-112">For example, the definition of a table requires that it contains at least one column to exist.</span></span> <span data-ttu-id="166a1-113">De même, une colonne ne peut pas exister séparément d'une table.</span><span class="sxs-lookup"><span data-stu-id="166a1-113">Also, a column cannot exist in isolation without a table.</span></span> <span data-ttu-id="166a1-114">Il existe une relation de codépendance entre la table et ses colonnes.</span><span class="sxs-lookup"><span data-stu-id="166a1-114">There is a codependent relationship between the table and its columns.</span></span>  
  
 <span data-ttu-id="166a1-115">La méthode <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> permet d'apporter des modifications à un objet.</span><span class="sxs-lookup"><span data-stu-id="166a1-115">The <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> method lets you make changes to an object.</span></span> <span data-ttu-id="166a1-116">Plusieurs modifications d'un objet, telles que l'ajout d'objets enfants à l'une des collections de l'objet ou la modification d'une valeur de propriété, sont regroupées et exécutées comme un tout.</span><span class="sxs-lookup"><span data-stu-id="166a1-116">Several changes to an object, such as adding child objects to one of the object's collections or changing a property value, are batched together and run as one.</span></span> <span data-ttu-id="166a1-117">La méthode `Alter` réduit le trafic réseau et améliore les performances globales.</span><span class="sxs-lookup"><span data-stu-id="166a1-117">The `Alter` method reduces network traffic and improves overall performance.</span></span>  
  
 <span data-ttu-id="166a1-118">L'instruction `Drop` est utilisée pour supprimer un objet et tous ses objets enfants codépendants requis pour créer initialement l'objet.</span><span class="sxs-lookup"><span data-stu-id="166a1-118">The `Drop` statement is used to remove an object and all its codependent child objects that were required to create the object initially.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="166a1-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="166a1-119">See Also</span></span>  
 [<span data-ttu-id="166a1-120">Modèle objet SMO</span><span class="sxs-lookup"><span data-stu-id="166a1-120">SMO Object Model</span></span>](../smo-object-model.md)  
  
  
