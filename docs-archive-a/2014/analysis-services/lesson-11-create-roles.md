---
title: 'Leçon 12 : créer des rôles | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 984face4-00fc-46d3-8ae1-9755bf737bdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 962cd19726a5404de81e20a2209b25b9cc277e21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600287"
---
# <a name="lesson-12-create-roles"></a><span data-ttu-id="d7d4b-102">Leçon 12 : Créer des rôles</span><span class="sxs-lookup"><span data-stu-id="d7d4b-102">Lesson 12: Create Roles</span></span>
  <span data-ttu-id="d7d4b-103">Dans cette leçon, vous allez créer des rôles.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-103">In this lesson, you will create roles.</span></span> <span data-ttu-id="d7d4b-104">Les rôles fournissent la sécurité des objets et des données d'une base de données de modèles, en limitant l'accès aux utilisateurs Windows qui y sont membres.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-104">Roles provide model database object and data security by limiting access to only those Windows users which are role members.</span></span> <span data-ttu-id="d7d4b-105">Chaque rôle est défini avec une autorisation unique : aucune autorisation, autorisation de lecture, autorisation de lecture et de traitement, autorisation de traitement ou autorisation d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-105">Each role is defined with a single permission: None, Read, Read and Process, Process, or Administrator.</span></span> <span data-ttu-id="d7d4b-106">Les rôles peuvent être définis lors de la création du modèle à l'aide de la boîte de dialogue Gestionnaire de rôles de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7d4b-106">Roles can be defined during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="d7d4b-107">Une fois le modèle déployé, vous pouvez gérer les rôles à l'aide de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7d4b-107">After a model has been deployed, you can manage roles by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d7d4b-108">Pour plus d’informations, consultez [Rôles &#40;SSAS Tabulaire&#41;](tabular-models/roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d7d4b-108">To learn more, see [Roles &#40;SSAS Tabular&#41;](tabular-models/roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7d4b-109">La création de rôles n'est pas nécessaire pour effectuer ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-109">Creating roles is not necessary to complete this tutorial.</span></span> <span data-ttu-id="d7d4b-110">Par défaut, le compte avec lequel vous êtes actuellement connecté disposera de privilèges Administrateur sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-110">By default, the account you are currently logged in with will have Administrator privileges on the model.</span></span> <span data-ttu-id="d7d4b-111">Toutefois, pour permettre à d'autres utilisateurs de votre organisation de parcourir le modèle à l'aide d'une application cliente de création de rapports, vous devez créer au moins un rôle avec des autorisations de lecture et ajouter ces utilisateurs en tant que membres.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-111">However, to allow other users in your organization to browse the model by using a reporting client application, you must create at least one role with Read permissions and add those users as members.</span></span>  
  
 <span data-ttu-id="d7d4b-112">Vous allez créer trois rôles :</span><span class="sxs-lookup"><span data-stu-id="d7d4b-112">You will create three roles:</span></span>  
  
-   <span data-ttu-id="d7d4b-113">Responsable des ventes : ce rôle peut inclure les utilisateurs de votre organisation pour lesquels vous souhaitez disposer d’une autorisation de lecture sur tous les objets de modèle et données.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-113">Sales Manager - This role can include users in your organization for which you want to have Read permission to all model objects and data.</span></span>  
  
-   <span data-ttu-id="d7d4b-114">Analyste des ventes-États-Unis : ce rôle peut inclure les utilisateurs de votre organisation pour lesquels vous souhaitez uniquement pouvoir parcourir les données relatives aux ventes aux États-Unis (États-Unis).</span><span class="sxs-lookup"><span data-stu-id="d7d4b-114">Sales Analyst US - This role can include users in your organization for which you want only to be able to browse data related to sales in the US (United States).</span></span> <span data-ttu-id="d7d4b-115">Pour ce rôle, vous utilisez une formule DAX pour définir un *filtre de lignes*, qui limite l’accès des membres aux seules données concernant les États-Unis.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-115">For this role, you will use a DAX formula to define a *Row Filter*, which restricts members to browse data only for the United States.</span></span>  
  
-   <span data-ttu-id="d7d4b-116">Administrateur : ce rôle peut inclure des utilisateurs pour lesquels vous souhaitez disposer d’une autorisation d’administrateur, qui permet un accès et des autorisations illimités pour effectuer des tâches d’administration sur la base de données model.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-116">Administrator - This role can include users for which you want to have Administrator permission, which allows unlimited access and permissions to perform administrative tasks on the model database.</span></span>  
  
 <span data-ttu-id="d7d4b-117">Étant donné que les comptes d'utilisateurs et de groupes Windows dans votre organisation sont uniques, vous pouvez ajouter des comptes de votre organisation aux membres.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-117">Because Windows user and group accounts in your organization are unique, you can add accounts from your particular organization to members.</span></span> <span data-ttu-id="d7d4b-118">Toutefois, pour ce didacticiel, vous pouvez également laissez les membres vides.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-118">However, for this tutorial, you can also leave the members blank.</span></span> <span data-ttu-id="d7d4b-119">Vous pourrez toujours tester l'effet de chaque rôle plus loin dans la leçon 12 : analyser dans Excel.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-119">You will still be able to test the effect of each role later in Lesson 12: Analyze in Excel.</span></span>  
  
 <span data-ttu-id="d7d4b-120">Durée estimée pour suivre cette leçon : **15 minutes**</span><span class="sxs-lookup"><span data-stu-id="d7d4b-120">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d7d4b-121">Prérequis</span><span class="sxs-lookup"><span data-stu-id="d7d4b-121">Prerequisites</span></span>  
 <span data-ttu-id="d7d4b-122">Cette rubrique fait partie d’un didacticiel de modélisation tabulaire, qui doit être suivi dans l’ordre prévu.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-122">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="d7d4b-123">Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [Leçon 11 : Créer des partitions](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="d7d4b-123">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
## <a name="create-roles"></a><span data-ttu-id="d7d4b-124">Créer les rôles</span><span class="sxs-lookup"><span data-stu-id="d7d4b-124">Create Roles</span></span>  
  
#### <a name="to-create-a-sales-manager-user-role"></a><span data-ttu-id="d7d4b-125">Pour créer un rôle d’utilisateur Sales Manager (Responsable des ventes)</span><span class="sxs-lookup"><span data-stu-id="d7d4b-125">To create a Sales Manager user role</span></span>  
  
1.  <span data-ttu-id="d7d4b-126">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis sur **Rôles**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-126">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="d7d4b-127">Dans la boîte de dialogue **Gestionnaire de rôles** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-127">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="d7d4b-128">Un nouveau rôle avec l’autorisation Aucune est ajouté à la liste.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-128">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="d7d4b-129">Cliquez sur le nouveau rôle, puis dans la colonne **nom** , renommez le rôle `Internet Sales Manager` .</span><span class="sxs-lookup"><span data-stu-id="d7d4b-129">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Manager`.</span></span>  
  
4.  <span data-ttu-id="d7d4b-130">Dans la colonne **Autorisations**, cliquez sur la liste déroulante et sélectionnez l’autorisation **Lecture**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-130">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="d7d4b-131">Facultatif : Cliquez sur l’onglet **Membres**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-131">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="d7d4b-132">Dans la boîte de dialogue **Sélectionner des utilisateurs ou des groupes**, entrez les utilisateurs ou les groupes Windows de votre organisation à inclure dans le rôle.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-132">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
7.  <span data-ttu-id="d7d4b-133">Vérifiez vos sélections, puis cliquez sur **OK** .</span><span class="sxs-lookup"><span data-stu-id="d7d4b-133">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-a-sales-analyst-us-user-role"></a><span data-ttu-id="d7d4b-134">Pour créer un rôle d'utilisateur Sales Analyst US</span><span class="sxs-lookup"><span data-stu-id="d7d4b-134">To create a Sales Analyst US user role</span></span>  
  
1.  <span data-ttu-id="d7d4b-135">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis sur **Rôles**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-135">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="d7d4b-136">Dans la boîte de dialogue **Gestionnaire de rôles** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-136">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="d7d4b-137">Un nouveau rôle avec l’autorisation Aucune est ajouté à la liste.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-137">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="d7d4b-138">Cliquez sur le nouveau rôle, puis dans la colonne **nom** , renommez le rôle `Internet Sales US` .</span><span class="sxs-lookup"><span data-stu-id="d7d4b-138">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales US`.</span></span>  
  
4.  <span data-ttu-id="d7d4b-139">Dans la colonne **Autorisations**, cliquez sur la liste déroulante et sélectionnez l’autorisation **Lecture**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-139">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="d7d4b-140">Cliquez sur l’onglet Filtres de lignes puis, pour la table **Geography** uniquement, dans la colonne Filtre DAX, tapez la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="d7d4b-140">Click on the Row Filters tab, and then for the **Geography** table only, in the DAX Filter column, type the following formula:</span></span>  
  
     `=Geography[Country Region Code] = "US"`  
  
     <span data-ttu-id="d7d4b-141">Une formule de filtre de lignes doit être résolue en une valeur booléenne (TRUE/FALSE).</span><span class="sxs-lookup"><span data-stu-id="d7d4b-141">A Row Filter formula must resolve to a Boolean (TRUE/FALSE) value.</span></span> <span data-ttu-id="d7d4b-142">Avec cette formule, vous spécifiez que seules les lignes avec la valeur de code Country Region « US » sont visibles par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-142">With this formula, you are specifying that only rows with the Country Region Code value of "US" be visible to the user.</span></span>  
  
     <span data-ttu-id="d7d4b-143">Lorsque vous avez terminé de générer la formule, appuyez sur ENTRÉE pour l'accepter.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-143">When you have finished building the formula, press ENTER.</span></span>  
  
6.  <span data-ttu-id="d7d4b-144">Facultatif : Cliquez sur l’onglet **Membres**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-144">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="d7d4b-145">Dans la boîte de dialogue **Sélectionner des utilisateurs ou des groupes**, entrez les utilisateurs ou les groupes Windows de votre organisation à inclure dans le rôle.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-145">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
8.  <span data-ttu-id="d7d4b-146">Vérifiez vos sélections, puis cliquez sur **OK** .</span><span class="sxs-lookup"><span data-stu-id="d7d4b-146">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-an-administrator-role"></a><span data-ttu-id="d7d4b-147">Pour créer un rôle d'administrateur</span><span class="sxs-lookup"><span data-stu-id="d7d4b-147">To create an Administrator role</span></span>  
  
1.  <span data-ttu-id="d7d4b-148">Dans la boîte de dialogue **Gestionnaire de rôles** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-148">In the **Role Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="d7d4b-149">Cliquez sur le nouveau rôle, puis dans la colonne **nom** , renommez le rôle `Internet Sales Administrator` .</span><span class="sxs-lookup"><span data-stu-id="d7d4b-149">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Administrator`.</span></span>  
  
3.  <span data-ttu-id="d7d4b-150">Dans la colonne **Autorisations** , cliquez sur la liste déroulante, puis sélectionnez l’autorisation **Administrateur** .</span><span class="sxs-lookup"><span data-stu-id="d7d4b-150">In the **Permissions** column, click the dropdown list, and then select the **Administrator** permission.</span></span>  
  
4.  <span data-ttu-id="d7d4b-151">Cliquez sur l’onglet **Membres** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-151">Click on the **Members** tab, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="d7d4b-152">Facultatif : dans la boîte de dialogue **Sélectionner des utilisateurs ou des groupes** , entrez les utilisateurs ou les groupes Windows de votre organisation à inclure dans le rôle.</span><span class="sxs-lookup"><span data-stu-id="d7d4b-152">Optional: In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
6.  <span data-ttu-id="d7d4b-153">Vérifiez vos sélections, puis cliquez sur **OK** .</span><span class="sxs-lookup"><span data-stu-id="d7d4b-153">Verify your selections, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d7d4b-154">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d7d4b-154">Next Steps</span></span>  
 <span data-ttu-id="d7d4b-155">Pour continuer ce didacticiel, passez à la leçon suivante : [Leçon 13 : Analyser dans Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="d7d4b-155">To continue this tutorial, go to the next lesson: Lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
  
