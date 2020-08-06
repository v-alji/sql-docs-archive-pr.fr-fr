---
title: Référence de l’interface utilisateur de la boîte de dialogue Suggérer les types de colonnes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.suggestdatatypes.f1
ms.assetid: 8d5652e0-cf57-483f-828b-10f00c08418b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbca2a3186a58b1148eb9627825fdfddf334339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708540"
---
# <a name="suggest-column-types-dialog-box-ui-reference"></a><span data-ttu-id="7f369-102">Référence de l'interface utilisateur de la boîte de dialogue Suggérer les types de colonnes</span><span class="sxs-lookup"><span data-stu-id="7f369-102">Suggest Column Types Dialog Box UI Reference</span></span>
  <span data-ttu-id="7f369-103">Utilisez la boîte de dialogue **Suggérer les types de colonnes** pour identifier le type de données et la longueur des colonnes dans un gestionnaire de connexions de fichiers plats en se basant sur un échantillonnage du contenu du fichier.</span><span class="sxs-lookup"><span data-stu-id="7f369-103">Use the **Suggest Column Types** dialog box to identify the data type and length of columns in a Flat File Connection Manager based on a sampling of the file content.</span></span>  
  
 <span data-ttu-id="7f369-104">Pour en savoir plus sur les types de données utilisés par [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f369-104">To learn more about the data types used by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f369-105">Options</span><span class="sxs-lookup"><span data-stu-id="7f369-105">Options</span></span>  
 <span data-ttu-id="7f369-106">**Nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="7f369-106">**Number of rows**</span></span>  
 <span data-ttu-id="7f369-107">Tapez ou sélectionnez le nombre de lignes de l'échantillon utilisées par l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="7f369-107">Type or select the number of rows in the sample that the algorithm uses.</span></span>  
  
 <span data-ttu-id="7f369-108">**Suggérer le plus petit type de données integer**</span><span class="sxs-lookup"><span data-stu-id="7f369-108">**Suggest the smallest integer data type**</span></span>  
 <span data-ttu-id="7f369-109">Désactivez cette case à cocher pour ignorer l'évaluation.</span><span class="sxs-lookup"><span data-stu-id="7f369-109">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="7f369-110">Si elle est activée, détermine le plus petit type de données integer possible pour les colonnes contenant des données numériques entières.</span><span class="sxs-lookup"><span data-stu-id="7f369-110">If selected, determines the smallest possible integer data type for columns that contain integral numeric data.</span></span>  
  
 <span data-ttu-id="7f369-111">**Suggérer le plus petit type de données real**</span><span class="sxs-lookup"><span data-stu-id="7f369-111">**Suggest the smallest real data type**</span></span>  
 <span data-ttu-id="7f369-112">Désactivez cette case à cocher pour ignorer l'évaluation.</span><span class="sxs-lookup"><span data-stu-id="7f369-112">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="7f369-113">Si elle est activée, détermine si les colonnes contenant des données numériques réelles peuvent utiliser le plus petit type de données real, DT_R4.</span><span class="sxs-lookup"><span data-stu-id="7f369-113">If selected, determines whether columns that contain real numeric data can use the smaller real data type, DT_R4.</span></span>  
  
 <span data-ttu-id="7f369-114">**Identifier les colonnes booléennes en utilisant les valeurs suivantes**</span><span class="sxs-lookup"><span data-stu-id="7f369-114">**Identify Boolean columns using the following values**</span></span>  
 <span data-ttu-id="7f369-115">Tapez les deux valeurs à utiliser en tant que valeurs booléennes True et False.</span><span class="sxs-lookup"><span data-stu-id="7f369-115">Type the two values that you want to use as the Boolean values true and false.</span></span> <span data-ttu-id="7f369-116">Ces valeurs doivent être séparées par une virgule, la première correspondant à la valeur True.</span><span class="sxs-lookup"><span data-stu-id="7f369-116">The values must be separated by a comma, and the first value represents True.</span></span>  
  
 <span data-ttu-id="7f369-117">**Remplir les colonnes de la chaîne**</span><span class="sxs-lookup"><span data-stu-id="7f369-117">**Pad string columns**</span></span>  
 <span data-ttu-id="7f369-118">Activez cette case à cocher pour autoriser le remplissage de la chaîne.</span><span class="sxs-lookup"><span data-stu-id="7f369-118">Select this check box to enable string padding.</span></span>  
  
 <span data-ttu-id="7f369-119">**Pourcentage de remplissage**</span><span class="sxs-lookup"><span data-stu-id="7f369-119">**Percent padding**</span></span>  
 <span data-ttu-id="7f369-120">Tapez ou sélectionnez le pourcentage des longueurs de colonnes à ajouter à la longueur des colonnes pour les données de type character.</span><span class="sxs-lookup"><span data-stu-id="7f369-120">Type or select the percentage of the column lengths by which to increase the length of columns for character data types.</span></span> <span data-ttu-id="7f369-121">Ce pourcentage doit être un nombre entier.</span><span class="sxs-lookup"><span data-stu-id="7f369-121">The percentage must be an integer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f369-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f369-122">See Also</span></span>  
 <span data-ttu-id="7f369-123">[Guide de référence des erreurs et des messages propres à Integration Services](../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7f369-123">[Integration Services Error and Message Reference](../integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="7f369-124">Gestionnaire de connexions de fichiers plats</span><span class="sxs-lookup"><span data-stu-id="7f369-124">Flat File Connection Manager</span></span>](file-connection-manager.md)  
  
  
