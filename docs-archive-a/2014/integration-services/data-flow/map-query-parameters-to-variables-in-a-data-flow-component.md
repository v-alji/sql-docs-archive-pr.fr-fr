---
title: Mapper des paramètres de requête à des variables dans un composant de flux de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 5e26977c-758c-46d6-acf1-4fd9238f0950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b38940313397c7be7a8bcdbd2bf7f5233583096e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708508"
---
# <a name="map-query-parameters-to-variables-in-a-data-flow-component"></a><span data-ttu-id="0adfe-102">Mapper des paramètres de requête à des variables dans un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="0adfe-102">Map Query Parameters to Variables in a Data Flow Component</span></span>
  <span data-ttu-id="0adfe-103">Lorsque vous configurez la source OLE DB pour utiliser des requêtes paramétrables, vous pouvez mapper les paramètres à des variables.</span><span class="sxs-lookup"><span data-stu-id="0adfe-103">When you configure the OLE DB source to use parameterized queries, you can map the parameters to variables.</span></span>  
  
 <span data-ttu-id="0adfe-104">La source OLE DB utilise des requêtes paramétrables pour filtrer les données lorsqu'elle se connecte à une source de données.</span><span class="sxs-lookup"><span data-stu-id="0adfe-104">The OLE DB source uses parameterized queries to filter data when the source connects to a data source.</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="0adfe-105">Pour mapper un paramètre de requête à une variable</span><span class="sxs-lookup"><span data-stu-id="0adfe-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="0adfe-106">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="0adfe-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0adfe-107">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="0adfe-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0adfe-108">Cliquez sur l'onglet **Flux de données** , puis dans la **Boîte à outils**, faites glisser la source OLE DB sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="0adfe-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="0adfe-109">Cliquez avec le bouton droit sur la source OLE DB, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="0adfe-109">Right-click the OLE DB source, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="0adfe-110">Dans l' **Éditeur de source OLE DB**, choisissez un gestionnaire de connexions OLE DB à utiliser pour se connecter à la source de données ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0adfe-110">In the **OLE DB Source Editor**, select an OLE DB connection manager to use to connect to the data source, or click **New** to create a new OLE DB connection manager.</span></span>  
  
6.  <span data-ttu-id="0adfe-111">Sélectionnez l'option **Commande SQL** comme mode d'accès aux données, puis tapez une requête paramétrable dans le volet **Texte de la commande SQL** .</span><span class="sxs-lookup"><span data-stu-id="0adfe-111">Select the **SQL command** option for data access mode, and then type a parameterized query in the **SQL command text** pane.</span></span>  
  
7.  <span data-ttu-id="0adfe-112">Cliquez sur **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="0adfe-112">Click **Parameters**.</span></span>  
  
8.  <span data-ttu-id="0adfe-113">Dans la boîte de dialogue **Définition des paramètres de la requête**, mappez chaque paramètre de la liste **Paramètres** à une variable de la liste **Variables** ou créez une variable en cliquant sur **\<New variable>** .</span><span class="sxs-lookup"><span data-stu-id="0adfe-113">In the **Set Query Parameters** dialog box, map each parameter in the **Parameters** list to a variable in the **Variables** list, or create a new variable by clicking **\<New variable>**.</span></span> <span data-ttu-id="0adfe-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0adfe-114">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0adfe-115">Seules les variables système et les variables définies par l'utilisateur qui se trouvent dans l'étendue du package, dans un conteneur parent tel qu'une boucle Foreach ou dans la tâche de flux de données contenant le composant de flux de données, peuvent être mappées.</span><span class="sxs-lookup"><span data-stu-id="0adfe-115">Only system variables and user-defined variables that are in the scope of the package, a parent container such as a Foreach Loop, or the Data Flow task that contains the data flow component are available for mapping.</span></span> <span data-ttu-id="0adfe-116">La variable doit avoir un type de données compatible avec la colonne de la clause WHERE à laquelle le paramètre est affecté.</span><span class="sxs-lookup"><span data-stu-id="0adfe-116">The variable must have a data type that is compatible with the column in the WHERE clause to which the parameter is assigned.</span></span>  
  
9. <span data-ttu-id="0adfe-117">Vous pouvez cliquer sur **Aperçu** pour afficher jusqu'à 200 lignes de données renvoyées par la requête.</span><span class="sxs-lookup"><span data-stu-id="0adfe-117">You can click **Preview** to view up to 200 rows of the data that the query returns.</span></span>  
  
10. <span data-ttu-id="0adfe-118">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="0adfe-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0adfe-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0adfe-119">See Also</span></span>  
 <span data-ttu-id="0adfe-120">[Source OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="0adfe-120">[OLE DB Source](ole-db-source.md) </span></span>  
 [<span data-ttu-id="0adfe-121">Transformation de recherche</span><span class="sxs-lookup"><span data-stu-id="0adfe-121">Lookup Transformation</span></span>](transformations/lookup-transformation.md)  
  
  
