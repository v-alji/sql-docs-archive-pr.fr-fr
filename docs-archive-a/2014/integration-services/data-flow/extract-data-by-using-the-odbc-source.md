---
title: Extraire des données à l’aide de la source ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 10f25703-49a2-4d45-abab-6b4da2a57ba5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c05efe2b0479047280fc093ee555e037c77d82e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709792"
---
# <a name="extract-data-by-using-the-odbc-source"></a><span data-ttu-id="ac948-102">Extraire des données à l'aide de la source ODBC</span><span class="sxs-lookup"><span data-stu-id="ac948-102">Extract Data by Using the ODBC Source</span></span>
  <span data-ttu-id="ac948-103">Cette procédure explique comment extraire des données à l'aide d'une source ODBC.</span><span class="sxs-lookup"><span data-stu-id="ac948-103">This procedure describes how to extract data by using an ODBC source.</span></span> <span data-ttu-id="ac948-104">Pour pouvoir ajouter et configurer une source ODBC, le package doit inclure au moins une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="ac948-104">To add and configure an ODBC source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-odbc-source"></a><span data-ttu-id="ac948-105">Pour extraire des données à l'aide d'une source ODBC</span><span class="sxs-lookup"><span data-stu-id="ac948-105">To extract data using an ODBC source</span></span>  
  
1.  <span data-ttu-id="ac948-106">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], ouvrez le package [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] souhaité.</span><span class="sxs-lookup"><span data-stu-id="ac948-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="ac948-107">Cliquez sur l'onglet **Flux de données** , puis dans la **Boîte à outils**, faites glisser la source ODBC sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="ac948-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC source to the design surface.</span></span>  
  
3.  <span data-ttu-id="ac948-108">Double-cliquez sur la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="ac948-108">Double-click the ODBC source.</span></span>  
  
4.  <span data-ttu-id="ac948-109">Dans la boîte de dialogue **Éditeur de source ODBC** , dans la page **Gestionnaire de connexions** , sélectionnez un gestionnaire de connexions ODBC existant ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="ac948-109">In the **ODBC Source Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="ac948-110">Sélectionnez la méthode d'accès aux données.</span><span class="sxs-lookup"><span data-stu-id="ac948-110">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="ac948-111">**Nom de la table**: sélectionnez une table ou une vue dans la base de données ou tapez une expression régulière pour identifier la table à laquelle le gestionnaire de connexions ODBC se connecte.</span><span class="sxs-lookup"><span data-stu-id="ac948-111">**Table Name**: Select a table or view in the database or type a regular expression to identify the table to which the ODBC connection manager connects.</span></span>  
  
         <span data-ttu-id="ac948-112">Cette liste contient les 1 000 premières tables uniquement.</span><span class="sxs-lookup"><span data-stu-id="ac948-112">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="ac948-113">Si votre base de données contient plus de 1 000 tables, vous pouvez taper le début du nom d'une table ou utiliser le caractère générique (\*) pour entrer une partie du nom afin d'afficher la table ou les tables que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="ac948-113">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
    -   <span data-ttu-id="ac948-114">**Commande SQL**: tapez une commande SQL ou cliquez sur **Parcourir** pour charger la requête SQL à partir d'un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="ac948-114">**SQL Command**: Type an SQL Command or click **Browse** to load the SQL query from a text file.</span></span>  
  
6.  <span data-ttu-id="ac948-115">Vous pouvez cliquer sur **Aperçu** pour afficher jusqu'à 200 lignes de données extraites par la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="ac948-115">You can click **Preview** to view up to 200 rows of the data extracted by the ODBC source.</span></span>  
  
7.  <span data-ttu-id="ac948-116">Pour mettre à jour le mappage entre les colonnes externes et les colonnes de sortie, cliquez sur **Colonnes** et sélectionnez des colonnes dans la liste **Colonne externe** .</span><span class="sxs-lookup"><span data-stu-id="ac948-116">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="ac948-117">Si nécessaire, mettez à jour les noms des colonnes de sortie en modifiant les valeurs dans la liste **Colonne de sortie** .</span><span class="sxs-lookup"><span data-stu-id="ac948-117">If necessary, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="ac948-118">Pour configurer l'affichage des erreurs, cliquez sur **Sortie d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="ac948-118">To configure the error output, click **Error Output**.</span></span>  
  
10. <span data-ttu-id="ac948-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac948-119">Click **OK**.</span></span>  
  
11. <span data-ttu-id="ac948-120">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="ac948-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac948-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac948-121">See Also</span></span>  
 <span data-ttu-id="ac948-122">[Éditeur de source ODBC &#40;page Gestionnaire de connexions&#41;](../odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ac948-122">[ODBC Source Editor &#40;Connection Manager Page&#41;](../odbc-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="ac948-123">[Éditeur de source ODBC &#40;page Colonnes&#41;](../odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="ac948-123">[ODBC Source Editor &#40;Columns Page&#41;](../odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="ac948-124">Éditeur de source ODBC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="ac948-124">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
