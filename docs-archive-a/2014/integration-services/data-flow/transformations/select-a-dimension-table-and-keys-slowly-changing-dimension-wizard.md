---
title: Sélectionner une table et des clés de dimension (Assistant Dimension à variation lente) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.selecttableandkeys.f1
ms.assetid: 01e0495f-de35-4607-ba19-0539e801e8fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 671c66a8a5d5f1f4f5201fd8c9ecc144540d8b68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710760"
---
# <a name="select-a-dimension-table-and-keys-slowly-changing-dimension-wizard"></a><span data-ttu-id="adaf8-102">Sélectionner une table et des clés de dimension (Assistant Dimension à variation lente)</span><span class="sxs-lookup"><span data-stu-id="adaf8-102">Select a Dimension Table and Keys (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="adaf8-103">Utilisez la page **Sélectionner une table et des clés de dimension** pour sélectionner une table de dimension à charger.</span><span class="sxs-lookup"><span data-stu-id="adaf8-103">Use the **Select a Dimension Table and Keys** page to select a dimension table to load.</span></span> <span data-ttu-id="adaf8-104">Mappez les colonnes du flux de données avec les colonnes qui vont être chargées.</span><span class="sxs-lookup"><span data-stu-id="adaf8-104">Map columns from the data flow to the columns that will be loaded.</span></span>  
  
 <span data-ttu-id="adaf8-105">Pour en savoir plus sur cet Assistant, consultez [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="adaf8-105">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="adaf8-106">Options</span><span class="sxs-lookup"><span data-stu-id="adaf8-106">Options</span></span>  
 <span data-ttu-id="adaf8-107">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="adaf8-107">**Connection manager**</span></span>  
 <span data-ttu-id="adaf8-108">Sélectionnez un gestionnaire de connexions OLE DB existant dans la liste ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions OLE DB.</span><span class="sxs-lookup"><span data-stu-id="adaf8-108">Select an existing OLE DB connection manager from the list, or click **New** to create an OLE DB connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="adaf8-109">L’Assistant Dimension à variation lente prend en charge les gestionnaires de connexions OLE DB et prend uniquement en charge les connexions à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adaf8-109">The Slowly Changing Dimension Wizard only supports OLE DB connection managers, and only supports connections to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="adaf8-110">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="adaf8-110">**New**</span></span>  
 <span data-ttu-id="adaf8-111">Utilisez la boîte de dialogue **Configurer le gestionnaire de connexions OLE DB** pour sélectionner un gestionnaire de connexions existant ou cliquez sur **Nouvelle** pour créer une nouvelle connexion OLE DB.</span><span class="sxs-lookup"><span data-stu-id="adaf8-111">Use the **Configure OLE DB Connection Manager** dialog box to select an existing connection manager, or click **New** to create a new OLE DB connection.</span></span>  
  
 <span data-ttu-id="adaf8-112">**Table ou vue**</span><span class="sxs-lookup"><span data-stu-id="adaf8-112">**Table or View**</span></span>  
 <span data-ttu-id="adaf8-113">Sélectionnez une table ou une vue dans la liste.</span><span class="sxs-lookup"><span data-stu-id="adaf8-113">Select a table or view from the list.</span></span>  
  
 <span data-ttu-id="adaf8-114">**Colonnes d'entrée**</span><span class="sxs-lookup"><span data-stu-id="adaf8-114">**Input Columns**</span></span>  
 <span data-ttu-id="adaf8-115">Sélectionnez dans la liste les colonnes d'entrée auxquelles vous voulez appliquer le mappage.</span><span class="sxs-lookup"><span data-stu-id="adaf8-115">Select from the list of input columns for which you may specify mapping.</span></span>  
  
 <span data-ttu-id="adaf8-116">**Colonnes de dimension**</span><span class="sxs-lookup"><span data-stu-id="adaf8-116">**Dimension Columns**</span></span>  
 <span data-ttu-id="adaf8-117">Affiche toutes les colonnes de dimension disponibles.</span><span class="sxs-lookup"><span data-stu-id="adaf8-117">View all available dimension columns.</span></span>  
  
 <span data-ttu-id="adaf8-118">**Type de clé**</span><span class="sxs-lookup"><span data-stu-id="adaf8-118">**Key Type**</span></span>  
 <span data-ttu-id="adaf8-119">Sélectionnez la colonne de dimension qui sera la clé d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="adaf8-119">Select one of the dimension columns to be the business key.</span></span> <span data-ttu-id="adaf8-120">Vous devez avoir une clé d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="adaf8-120">You must have one business key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adaf8-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="adaf8-121">See Also</span></span>  
 [<span data-ttu-id="adaf8-122">Configurer les sorties à l'aide de l'Assistant Dimension à variation lente</span><span class="sxs-lookup"><span data-stu-id="adaf8-122">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
