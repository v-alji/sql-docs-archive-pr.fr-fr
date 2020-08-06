---
title: Créer des scripts au moyen de modèles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ed48014c-3fc9-48ff-8c0f-8d1822195f14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b404ecc505e93c302e4c737f9c0b0161d9015519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702240"
---
# <a name="create-scripts-using-templates"></a><span data-ttu-id="ed01c-102">Créer des scripts au moyen de modèles</span><span class="sxs-lookup"><span data-stu-id="ed01c-102">Create Scripts Using Templates</span></span>
  <span data-ttu-id="ed01c-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fournit un grand nombre de modèles de scripts contenant les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] pour la plupart des tâches courantes.</span><span class="sxs-lookup"><span data-stu-id="ed01c-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides a large number of script templates containing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for many common tasks.</span></span> <span data-ttu-id="ed01c-104">Ces modèles contiennent des paramètres pour les valeurs fournies par les utilisateurs, telles que les noms des tables.</span><span class="sxs-lookup"><span data-stu-id="ed01c-104">These templates contain parameters for the user-provided values such as a table name.</span></span> <span data-ttu-id="ed01c-105">À l'aide de ces paramètres, vous pouvez taper un nom une fois puis le copier automatiquement partout où cela est nécessaire dans le script.</span><span class="sxs-lookup"><span data-stu-id="ed01c-105">Using the parameters, you can type the name once and then automatically copy the name to all the necessary locations within the script.</span></span> <span data-ttu-id="ed01c-106">Vous pouvez écrire vos propres modèles personnalisés pour prendre en compte les scripts que vous écrivez souvent.</span><span class="sxs-lookup"><span data-stu-id="ed01c-106">You can write your own custom templates to support the scripts that you write most often.</span></span> <span data-ttu-id="ed01c-107">Vous pouvez également réorganiser l'arborescence des modèles, déplacer des modèles ou créer de nouveaux dossiers pour y stocker des modèles.</span><span class="sxs-lookup"><span data-stu-id="ed01c-107">You can also reorganize the template tree, moving templates or creating new folders to hold the templates.</span></span> <span data-ttu-id="ed01c-108">Au cours de cet exercice, vous allez utiliser un modèle pour créer une base de données en spécifiant un modèle de classement.</span><span class="sxs-lookup"><span data-stu-id="ed01c-108">In the following practice, you will use a template to create a database, specifying collation template.</span></span>  
  
## <a name="using-templates"></a><span data-ttu-id="ed01c-109">Utilisation de modèles</span><span class="sxs-lookup"><span data-stu-id="ed01c-109">Using Templates</span></span>  
  
#### <a name="to-create-a-script-using-a-template"></a><span data-ttu-id="ed01c-110">Pour créer un script à l'aide d'un modèle</span><span class="sxs-lookup"><span data-stu-id="ed01c-110">To create a script using a template</span></span>  
  
1.  <span data-ttu-id="ed01c-111">Dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], dans le menu **Affichage** , cliquez sur **Explorateur de modèles**.</span><span class="sxs-lookup"><span data-stu-id="ed01c-111">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="ed01c-112">Dans l'Explorateur de modèles, les modèles sont organisés par groupe.</span><span class="sxs-lookup"><span data-stu-id="ed01c-112">The templates in Template Explorer are organized into groups.</span></span> <span data-ttu-id="ed01c-113">Développez **Base de données**, puis double-cliquez sur **Créer une base de données**.</span><span class="sxs-lookup"><span data-stu-id="ed01c-113">Expand **Database**, and then double-click **Create Database**.</span></span>  
  
3.  <span data-ttu-id="ed01c-114">Dans la boîte de dialogue **Se connecter au moteur de base de données** , fournissez les informations de connexion, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="ed01c-114">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="ed01c-115">Une nouvelle fenêtre de l’Éditeur de requête s’affiche et présente le contenu du modèle **Créer une base de données** .</span><span class="sxs-lookup"><span data-stu-id="ed01c-115">A new Query Editor window opens, containing the contents of the **Create Database** template.</span></span>  
  
4.  <span data-ttu-id="ed01c-116">Dans le menu **Requête** , cliquez sur **Spécifier les valeurs des paramètres du modèle**.</span><span class="sxs-lookup"><span data-stu-id="ed01c-116">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="ed01c-117">Dans la boîte de dialogue **Spécifier les valeurs des paramètres du modèle** , la colonne **Valeur** contient une valeur possible pour le paramètre **Database_Name** .</span><span class="sxs-lookup"><span data-stu-id="ed01c-117">In the **Specify Values for Template Parameters** dialog box, the **Value** column contains a suggested value for the **Database_Name** parameter.</span></span> <span data-ttu-id="ed01c-118">Dans la zone du paramètre **Nom de la base de données** , tapez **Marketing**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed01c-118">In the **Database Name** parameter box, type **Marketing**, and then click **OK**.</span></span> <span data-ttu-id="ed01c-119">Notez que « Marketing » est maintenant inséré à plusieurs endroits du script.</span><span class="sxs-lookup"><span data-stu-id="ed01c-119">Note how "Marketing" is inserted into the script in several locations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ed01c-120">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="ed01c-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ed01c-121">Créer des modèles personnalisés</span><span class="sxs-lookup"><span data-stu-id="ed01c-121">Create Custom Templates</span></span>](lesson-3-2-create-custom-templates.md)  
  
  
