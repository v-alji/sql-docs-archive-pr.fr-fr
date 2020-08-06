---
title: Barre d'état (éditeur de requête du moteur de base de données)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7f2d6f4-bb94-4cf5-a096-c34397e679af
author: rothja
ms.author: jroth
ms.openlocfilehash: 743ae0a4152daee19aa67f85337ae4077a3ed7f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612759"
---
# <a name="status-bar-database-engine-query-editor"></a><span data-ttu-id="5f553-102">Barre d'état (éditeur de requête du moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="5f553-102">Status Bar (Database Engine Query Editor)</span></span>
  <span data-ttu-id="5f553-103">La barre d'état des fenêtres de l'éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] peut être codée par couleur pour indiquer l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] auquel chaque fenêtre est connectée.</span><span class="sxs-lookup"><span data-stu-id="5f553-103">The status bar of [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor windows can be color coded to indicate which instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] each window is connected to.</span></span>  
  
1.  <span data-ttu-id="5f553-104">**Avant de commencer :**  [Couleurs de la barre d'état](#StatusBarColors)</span><span class="sxs-lookup"><span data-stu-id="5f553-104">**Before you begin:**  [Status Bar Colors](#StatusBarColors)</span></span>  
  
2.  <span data-ttu-id="5f553-105">**Pour définir une couleur d'état de serveur dans :**  [Explorateur d’objets](#SetOEServerColor), [Serveur inscrit](#SetRegServerColor)</span><span class="sxs-lookup"><span data-stu-id="5f553-105">**To set a server status color in:**  [Object Explorer](#SetOEServerColor), [Registered Server](#SetRegServerColor)</span></span>  
  
3.  <span data-ttu-id="5f553-106">**Pour utiliser une couleur d’état :**  [Ouvrir un Éditeur de requête à l'aide d'une couleur de serveur](#OpenServerColor), [Ouvrir un Éditeur de requête en spécifiant une couleur d'état](#OpenSpecColor)</span><span class="sxs-lookup"><span data-stu-id="5f553-106">**To use a status color:**  [Open Query Editor Using a Server Color](#OpenServerColor), [Open a Query Editor Specifying a Status Color](#OpenSpecColor)</span></span>  
  
##  <a name="status-bar-colors"></a><a name="StatusBarColors"></a> <span data-ttu-id="5f553-107">Couleurs de la barre d'état</span><span class="sxs-lookup"><span data-stu-id="5f553-107">Status Bar Colors</span></span>  
 <span data-ttu-id="5f553-108">Vous pouvez associer une couleur de barre d'état à un nœud serveur spécifique dans l' **Explorateur d'objets** ou dans **Serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="5f553-108">You can associate a status bar color with a specific server node in either **Object Explorer** or **Registered Servers**.</span></span> <span data-ttu-id="5f553-109">Les couleurs peuvent être spécifiées uniquement pour des nœuds serveurs connectés à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)], et non pour des nœuds serveurs pour d'autres technologies SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5f553-109">The colors can only be specified for server nodes connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], not server nodes for other SQL Server technologies.</span></span> <span data-ttu-id="5f553-110">Vous pouvez également spécifier une couleur de barre d'état personnalisée chaque fois que vous connectez une nouvelle fenêtre de l'Éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f553-110">You can also specify a custom status bar color each time you connect a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="5f553-111">Vous pouvez ensuite ouvrir une fenêtre d'Éditeur de requête soit en utilisant la couleur d'état définie pour le nœud serveur, soit en spécifiant une couleur unique pour cette fenêtre d'éditeur.</span><span class="sxs-lookup"><span data-stu-id="5f553-111">You can then open a query editor window using either the status color defined for the server node, or specify a unique color for that editor window.</span></span>  
  
 <span data-ttu-id="5f553-112">La définition d'une couleur de barre d'état personnalisée pour un nœud serveur dans l'Explorateur d'objets doit être effectuée lors de l'établissement de la connexion.</span><span class="sxs-lookup"><span data-stu-id="5f553-112">Setting a custom status bar color for a server node in Object Explorer must be done when making the connection.</span></span> <span data-ttu-id="5f553-113">Pour modifier la couleur associée à un nœud serveur existant, vous devez vous déconnecter puis vous reconnecter en spécifiant la nouvelle couleur.</span><span class="sxs-lookup"><span data-stu-id="5f553-113">To change the color associated with an existing server node, you must disconnect and then reconnect specifying the new color.</span></span>  
  
##  <a name="set-the-status-color-for-a-server-in-object-explorer"></a><a name="SetOEServerColor"></a> <span data-ttu-id="5f553-114">Définir la couleur d'état pour un serveur dans l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="5f553-114">Set the Status Color for a Server in Object Explorer</span></span>  
 <span data-ttu-id="5f553-115">**Pour définir une couleur d'état de serveur dans l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="5f553-115">**To set a server status color in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="5f553-116">Dans l’**Explorateur d’objets**, sélectionnez **Se connecter**, puis **Moteur de base de données...** .</span><span class="sxs-lookup"><span data-stu-id="5f553-116">In **Object Explorer**, select the **Connect** button and then select **Database Engine...**.</span></span>  
  
2.  <span data-ttu-id="5f553-117">Dans la boîte de dialogue **Se connecter au serveur**, sélectionnez **Options >>** .</span><span class="sxs-lookup"><span data-stu-id="5f553-117">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
3.  <span data-ttu-id="5f553-118">Activez la case à cocher **Utiliser une couleur personnalisée** .</span><span class="sxs-lookup"><span data-stu-id="5f553-118">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="5f553-119">Pour choisir la couleur, sélectionnez le bouton **Sélectionner...** .</span><span class="sxs-lookup"><span data-stu-id="5f553-119">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="5f553-120">Sélectionnez une couleur de base ou personnalisée, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5f553-120">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="5f553-121">Remplissez le reste des informations de connexion, puis cliquez sur le bouton **Se connecter** .</span><span class="sxs-lookup"><span data-stu-id="5f553-121">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
##  <a name="set-the-status-color-for-a-registered-server"></a><a name="SetRegServerColor"></a> <span data-ttu-id="5f553-122">Définir la couleur d'état pour un serveur inscrit</span><span class="sxs-lookup"><span data-stu-id="5f553-122">Set the Status Color For a Registered Server</span></span>  
 <span data-ttu-id="5f553-123">**Pour définir une couleur de serveur pour un serveur inscrit**</span><span class="sxs-lookup"><span data-stu-id="5f553-123">**To set a server color For a Registered Server**</span></span>  
  
1.  <span data-ttu-id="5f553-124">Dans **Serveurs inscrits**, cliquez avec le bouton droit sur le nœud de serveur, puis sélectionnez **Propriétés...** .</span><span class="sxs-lookup"><span data-stu-id="5f553-124">In **Registered Servers**, right click the server node and then select **Properties...**.</span></span>  
  
2.  <span data-ttu-id="5f553-125">Dans la boîte de dialogue **Modifier les propriétés d'inscription du serveur** , sélectionnez l'onglet **Propriétés de connexion** .</span><span class="sxs-lookup"><span data-stu-id="5f553-125">On the **Edit Server Registration Properties** dialog, select the **Connection Properties** tab.</span></span>  
  
3.  <span data-ttu-id="5f553-126">Activez la case à cocher **Utiliser une couleur personnalisée** .</span><span class="sxs-lookup"><span data-stu-id="5f553-126">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="5f553-127">Pour choisir la couleur, sélectionnez le bouton **Sélectionner...** .</span><span class="sxs-lookup"><span data-stu-id="5f553-127">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="5f553-128">Sélectionnez une couleur de base ou personnalisée, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5f553-128">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="5f553-129">Cliquez sur le bouton **Enregistrer** dans la boîte de dialogue **Modifier les propriétés d'inscription du serveur** .</span><span class="sxs-lookup"><span data-stu-id="5f553-129">Select the **Save** button on the **Edit Server Registration Properties** dialog.</span></span>  
  
##  <a name="open-an-editor-using-a-server-color"></a><a name="OpenServerColor"></a> <span data-ttu-id="5f553-130">Ouvrir un éditeur à l'aide d'une couleur de serveur</span><span class="sxs-lookup"><span data-stu-id="5f553-130">Open An Editor Using a Server Color</span></span>  
 <span data-ttu-id="5f553-131">**Pour ouvrir une fenêtre d'éditeur à l'aide d'une couleur de serveur**</span><span class="sxs-lookup"><span data-stu-id="5f553-131">**To open an editor window using a server color**</span></span>  
  
-   <span data-ttu-id="5f553-132">Cliquez avec le bouton droit sur un nœud serveur dans l’ **Explorateur d’objets** ou dans **Serveurs inscrits**, puis sélectionnez **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5f553-132">Right-click a server node in either **Object Explorer** or **Registered Servers**, and select **New Query**.</span></span>  
  
-   <span data-ttu-id="5f553-133">En guise d'alternative, mettez en surbrillance un nœud serveur, puis sélectionnez le bouton **Nouvelle requête** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="5f553-133">Alternatively, highlight a server node, and then select the **New Query** toolbar button.</span></span>  
  
-   <span data-ttu-id="5f553-134">La barre d'état dans la fenêtre de l'éditeur utilisera la couleur définie pour le serveur associé.</span><span class="sxs-lookup"><span data-stu-id="5f553-134">The status bar in the editor window will use the color defined for the associated server.</span></span>  
  
##  <a name="open-an-editor-specifying-a-status-color"></a><a name="OpenSpecColor"></a> <span data-ttu-id="5f553-135">Ouvrir un éditeur en spécifiant une couleur d'état</span><span class="sxs-lookup"><span data-stu-id="5f553-135">Open an Editor Specifying a Status Color</span></span>  
 <span data-ttu-id="5f553-136">**Pour ouvrir une fenêtre d'éditeur en spécifiant une couleur d'état**</span><span class="sxs-lookup"><span data-stu-id="5f553-136">**To open an editor window specifying a status color**</span></span>  
  
-   <span data-ttu-id="5f553-137">Ouvrez le menu **Fichier** , sélectionnez **Nouveau**, puis **Requête de moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="5f553-137">Open the **File** menu, select **New**, and then select **Database Engine Query**.</span></span>  
  
-   <span data-ttu-id="5f553-138">Dans la boîte de dialogue **Se connecter au serveur**, sélectionnez **Options >>** .</span><span class="sxs-lookup"><span data-stu-id="5f553-138">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
-   <span data-ttu-id="5f553-139">Activez la case à cocher **Utiliser une couleur personnalisée** .</span><span class="sxs-lookup"><span data-stu-id="5f553-139">Select the **Use custom color** check box.</span></span>  
  
-   <span data-ttu-id="5f553-140">Pour choisir la couleur, sélectionnez le bouton **Sélectionner...** .</span><span class="sxs-lookup"><span data-stu-id="5f553-140">To select the color, select the **Select...** button.</span></span>  
  
-   <span data-ttu-id="5f553-141">Sélectionnez une couleur de base ou personnalisée, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="5f553-141">Select either a basic or custom color, then select OK.</span></span>  
  
-   <span data-ttu-id="5f553-142">Remplissez le reste des informations de connexion, puis cliquez sur le bouton **Se connecter** .</span><span class="sxs-lookup"><span data-stu-id="5f553-142">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f553-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f553-143">See Also</span></span>  
 [<span data-ttu-id="5f553-144">Éditeurs de texte et de requête &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5f553-144">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](../scripting/query-and-text-editors-sql-server-management-studio.md)  
  
  
