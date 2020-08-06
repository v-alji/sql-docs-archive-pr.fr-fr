---
title: Activer et désactiver les sandboxing RDL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d5619e9f-ec5b-4376-9b34-1f74de6fade7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7af1477751093862c99d00978278315e600511e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703887"
---
# <a name="enable-and-disable-rdl-sandboxing"></a><span data-ttu-id="3dba7-102">Activer et désactiver sandboxing RDL</span><span class="sxs-lookup"><span data-stu-id="3dba7-102">Enable and Disable RDL Sandboxing</span></span>
  <span data-ttu-id="3dba7-103">La fonctionnalité Sandboxing RDL (Report Definition Language) vous permet de détecter et restreindre l'utilisation de types spécifiques de ressources, par les locataires individuels, dans un environnement où plusieurs locataires utilisent une batterie de serveurs Web unique de serveurs de rapports.</span><span class="sxs-lookup"><span data-stu-id="3dba7-103">The RDL (Report Definition Language) Sandboxing feature lets you detect and restrict the usage of specific types of resources, by individual tenants, in an environment of multiple tenants that use a single web farm of report servers.</span></span> <span data-ttu-id="3dba7-104">Citons pour exemple un scénario de services d'hébergement où vous pouvez maintenir une batterie de serveurs Web uniques de serveurs de rapports utilisés par plusieurs locataires, et peut-être différentes sociétés.</span><span class="sxs-lookup"><span data-stu-id="3dba7-104">An example of this is a hosting services scenario where you might maintain a single web farm of report servers that are used by multiple tenants, and perhaps different companies.</span></span> <span data-ttu-id="3dba7-105">En tant qu'administrateur de serveur de rapports, vous pouvez activer cette fonctionnalité pour aider à accomplir les objectifs suivants :</span><span class="sxs-lookup"><span data-stu-id="3dba7-105">As a report server administrator, you can enable this feature to help achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="3dba7-106">Restreindre la taille des ressources externes.</span><span class="sxs-lookup"><span data-stu-id="3dba7-106">Restrict external resource sizes.</span></span> <span data-ttu-id="3dba7-107">Les ressources externes incluent les images, fichiers .xslt et données cartographiques.</span><span class="sxs-lookup"><span data-stu-id="3dba7-107">External resources include images, .xslt files, and map data.</span></span>  
  
-   <span data-ttu-id="3dba7-108">Lors de la publication des rapports, limiter les types et membres utilisés dans le texte d'expression.</span><span class="sxs-lookup"><span data-stu-id="3dba7-108">At report publish time, limit types and members that are used in expression text.</span></span>  
  
-   <span data-ttu-id="3dba7-109">Lors du traitement des rapports, limiter la longueur du texte et la taille de la valeur de retour pour les expressions.</span><span class="sxs-lookup"><span data-stu-id="3dba7-109">At report processing time, limit the length of the text and the size of the return value for expressions.</span></span>  
  
 <span data-ttu-id="3dba7-110">Lorsque le Sandboxing RDL est activé, les fonctionnalités suivantes sont désactivées :</span><span class="sxs-lookup"><span data-stu-id="3dba7-110">When RDL Sandboxing is enabled, the following features are disabled:</span></span>  
  
-   <span data-ttu-id="3dba7-111">Code personnalisé dans l' **\<Code>** élément d’une définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="3dba7-111">Custom code in the **\<Code>** element of a report definition.</span></span>  
  
-   <span data-ttu-id="3dba7-112">Mode de compatibilité descendante RDL pour les éléments de rapport personnalisé [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3dba7-112">RDL backward compatibility mode for [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] custom report items.</span></span>  
  
-   <span data-ttu-id="3dba7-113">Paramètres nommés dans les expressions</span><span class="sxs-lookup"><span data-stu-id="3dba7-113">Named parameters in expressions.</span></span>  
  
 <span data-ttu-id="3dba7-114">Cette rubrique décrit chaque élément de l' `RDLSandboxing` élément <> dans le fichier RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="3dba7-114">This topic describes each element in the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span> <span data-ttu-id="3dba7-115">Pour plus d’informations sur la modification de ce fichier, consultez [Modifier un fichier de configuration Reporting Services &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="3dba7-115">For more information about how to modify this file, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="3dba7-116">Un journal des traces de serveur enregistre l'activité liée à la fonctionnalité Sandboxing RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-116">A server trace log records activity related to the RDL Sandboxing feature.</span></span> <span data-ttu-id="3dba7-117">Pour plus d’informations sur les journaux des traces, consultez [Journal des traces du service Report Server](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="3dba7-117">For more information about trace logs, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="3dba7-118">Exemple de configuration</span><span class="sxs-lookup"><span data-stu-id="3dba7-118">Example Configuration</span></span>  
 <span data-ttu-id="3dba7-119">L’exemple suivant montre les paramètres et des exemples de valeurs pour l' `RDLSandboxing` élément <> dans le fichier RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="3dba7-119">The following example shows the settings and example values for the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span>  
  
```  
<RDLSandboxing>  
   <MaxExpressionLength>5000</MaxExpressionLength>  
   <MaxResourceSize>5000</MaxResourceSize>  
   <MaxStringResultLength>3000</MaxStringResultLength>  
   <MaxArrayResultLength>250</MaxArrayResultLength>  
   <Types>  
      <Allow Namespace="System.Drawing" AllowNew="True">Bitmap</Allow>  
      <Allow Namespace="TypeConverters.Custom" AllowNew="True">*</Allow>  
   </Types>  
   <Members>  
      <Deny>Format</Deny>  
      <Deny>StrDup</Deny>  
   </Members>  
</RDLSandboxing>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="3dba7-120">Paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="3dba7-120">Configuration Settings</span></span>  
 <span data-ttu-id="3dba7-121">Le tableau suivant contient des informations sur les paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="3dba7-121">The following table provides information about configuration settings.</span></span> <span data-ttu-id="3dba7-122">Les paramètres sont présentés dans l'ordre dans lequel ils apparaissent dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="3dba7-122">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="3dba7-123">Paramètre</span><span class="sxs-lookup"><span data-stu-id="3dba7-123">Setting</span></span>|<span data-ttu-id="3dba7-124">Description</span><span class="sxs-lookup"><span data-stu-id="3dba7-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3dba7-125">**MaxExpressionLength**</span><span class="sxs-lookup"><span data-stu-id="3dba7-125">**MaxExpressionLength**</span></span>|<span data-ttu-id="3dba7-126">Quantité maximale de caractères autorisés dans les expressions RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-126">Maximum number of characters allowed in RDL expressions.</span></span><br /><br /> <span data-ttu-id="3dba7-127">Valeur par défaut : 1000</span><span class="sxs-lookup"><span data-stu-id="3dba7-127">Default: 1000</span></span>|  
|<span data-ttu-id="3dba7-128">**MaxResourceSize**</span><span class="sxs-lookup"><span data-stu-id="3dba7-128">**MaxResourceSize**</span></span>|<span data-ttu-id="3dba7-129">Quantité maximale de Ko autorisés pour une ressource externe.</span><span class="sxs-lookup"><span data-stu-id="3dba7-129">Maximum number of KB allowed for an external resource.</span></span><br /><br /> <span data-ttu-id="3dba7-130">Valeur par défaut : 100</span><span class="sxs-lookup"><span data-stu-id="3dba7-130">Default: 100</span></span>|  
|<span data-ttu-id="3dba7-131">**MaxStringResultLength**</span><span class="sxs-lookup"><span data-stu-id="3dba7-131">**MaxStringResultLength**</span></span>|<span data-ttu-id="3dba7-132">Quantité maximale de caractères autorisés dans une valeur de retour pour une expression RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-132">Maximum number of characters allowed in a return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="3dba7-133">Valeur par défaut : 1000</span><span class="sxs-lookup"><span data-stu-id="3dba7-133">Default: 1000</span></span>|  
|<span data-ttu-id="3dba7-134">**MaxArrayResultLength**</span><span class="sxs-lookup"><span data-stu-id="3dba7-134">**MaxArrayResultLength**</span></span>|<span data-ttu-id="3dba7-135">Quantité maximale d'éléments autorisés dans un tableau de valeurs retourné pour une expression RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-135">Maximum number of items allowed in an array return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="3dba7-136">Valeur par défaut : 100</span><span class="sxs-lookup"><span data-stu-id="3dba7-136">Default: 100</span></span>|  
|<span data-ttu-id="3dba7-137">**Types**</span><span class="sxs-lookup"><span data-stu-id="3dba7-137">**Types**</span></span>|<span data-ttu-id="3dba7-138">Liste des membres à autoriser dans les expressions RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-138">The list of members to allow within RDL expressions.</span></span>|  
|<span data-ttu-id="3dba7-139">**Autoriser**</span><span class="sxs-lookup"><span data-stu-id="3dba7-139">**Allow**</span></span>|<span data-ttu-id="3dba7-140">Type ou jeu de types à autoriser dans les expressions RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-140">A type or set of types to allow in RDL expressions.</span></span>|  
|<span data-ttu-id="3dba7-141">**Espace de noms**</span><span class="sxs-lookup"><span data-stu-id="3dba7-141">**Namespace**</span></span>|<span data-ttu-id="3dba7-142">Attribut pour **Allow** qui est l’espace de noms contenant un ou plusieurs types qui s’appliquent à Valeur.</span><span class="sxs-lookup"><span data-stu-id="3dba7-142">Attribute for **Allow** that is the namespace that contains one or more types that apply to Value.</span></span> <span data-ttu-id="3dba7-143">Cette propriété n'est pas sensible à la casse.</span><span class="sxs-lookup"><span data-stu-id="3dba7-143">This property is case-insensitive.</span></span>|  
|`AllowNew`|<span data-ttu-id="3dba7-144">Attribut booléen pour **allow** qui contrôle si la création de nouvelles instances du type est autorisée dans les expressions RDL ou dans un **\<Class>** élément RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-144">Boolean attribute for **Allow** that controls whether new instances of the type are allowed to be created in RDL expressions or in an RDL **\<Class>** element.</span></span><br /><br /> <span data-ttu-id="3dba7-145">Remarque : lorsque `RDLSandboxing` est activé, les nouveaux tableaux ne peuvent pas être créés dans les expressions RDL, quel que soit le paramètre de `AllowNew` .</span><span class="sxs-lookup"><span data-stu-id="3dba7-145">Note: When `RDLSandboxing` is enabled, new arrays cannot be created in RDL expressions, regardless of the setting of `AllowNew`.</span></span>|  
|<span data-ttu-id="3dba7-146">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="3dba7-146">**Value**</span></span>|<span data-ttu-id="3dba7-147">Valeur pour **Allow** qui est le nom du type à autoriser dans les expressions RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-147">Value for **Allow** that is the name of the type to allow in RDL expressions.</span></span> <span data-ttu-id="3dba7-148">La valeur **\*** indique que tous les types de l’espace de noms sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="3dba7-148">The value **\*** indicates that all types in the namespace are allowed.</span></span> <span data-ttu-id="3dba7-149">Cette propriété n'est pas sensible à la casse.</span><span class="sxs-lookup"><span data-stu-id="3dba7-149">This property is case-insensitive.</span></span>|  
|<span data-ttu-id="3dba7-150">**Membres**</span><span class="sxs-lookup"><span data-stu-id="3dba7-150">**Members**</span></span>|<span data-ttu-id="3dba7-151">Pour obtenir la liste des types qui sont inclus dans l' **\<Types>** élément, la liste des noms de membres qui ne sont pas autorisés dans les expressions RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-151">For the list of types that are include in the **\<Types>** element, the list of member names that are not allowed in RDL expressions.</span></span>|  
|<span data-ttu-id="3dba7-152">**Deny**</span><span class="sxs-lookup"><span data-stu-id="3dba7-152">**Deny**</span></span>|<span data-ttu-id="3dba7-153">Nom d'un membre qui n'est pas autorisé dans les expressions RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-153">The name of a member that is not allowed in RDL expressions.</span></span> <span data-ttu-id="3dba7-154">Cette propriété n'est pas sensible à la casse.</span><span class="sxs-lookup"><span data-stu-id="3dba7-154">This property is case-insensitive.</span></span><br /><br /> <span data-ttu-id="3dba7-155">Remarque : Quand **Deny** est spécifié pour un membre, tous les membres portant ce nom pour tous les types ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="3dba7-155">Note: When **Deny** is specified for a member, all members with this name for all types are not allowed.</span></span>|  
  
## <a name="working-with-expressions-when-rdl-sandboxing-is-enabled"></a><span data-ttu-id="3dba7-156">Utilisation des expressions lorsque le Sandboxing RDL est activé</span><span class="sxs-lookup"><span data-stu-id="3dba7-156">Working with Expressions when RDL Sandboxing is Enabled</span></span>  
 <span data-ttu-id="3dba7-157">Vous pouvez modifier la fonctionnalité Sandboxing RDL afin d'aider à gérer les ressources utilisées par une expression des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="3dba7-157">You can modify the RDL Sandboxing feature to help manage the resources that are used by an expression in the following ways:</span></span>  
  
-   <span data-ttu-id="3dba7-158">Limitez le nombre de caractères utilisés pour une expression.</span><span class="sxs-lookup"><span data-stu-id="3dba7-158">Restrict the number of characters that are used for an expression.</span></span>  
  
-   <span data-ttu-id="3dba7-159">Limitez la taille du résultat retourné par une expression.</span><span class="sxs-lookup"><span data-stu-id="3dba7-159">Restrict the size of the result returned by an expression.</span></span>  
  
-   <span data-ttu-id="3dba7-160">Autorisez une liste spécifique de types qui peuvent être utilisés dans une expression.</span><span class="sxs-lookup"><span data-stu-id="3dba7-160">Allow a specific list of types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="3dba7-161">Limitez la liste de membres par nom pour la liste des types autorisés qui peuvent être utilisés dans une expression.</span><span class="sxs-lookup"><span data-stu-id="3dba7-161">Restrict the list of members by name for the list of allowed types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="3dba7-162">La fonctionnalité Sandboxing RDL vous permet de créer une liste de types approuvés et une liste de membres refusés.</span><span class="sxs-lookup"><span data-stu-id="3dba7-162">The RDL Sandboxing feature enables you to create a list of approved types and a list of denied members.</span></span> <span data-ttu-id="3dba7-163">La liste des types approuvés porte le nom de liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-163">The list of approved types is called an allow list.</span></span> <span data-ttu-id="3dba7-164">La liste des membres refusés porte le nom de liste rouge.</span><span class="sxs-lookup"><span data-stu-id="3dba7-164">The list of denied members is called a block list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3dba7-165">Dans la définition de rapport, un ordinateur ne peut pas connaître le type de chaque instance d'une référence d'expression.</span><span class="sxs-lookup"><span data-stu-id="3dba7-165">In the report definition, a computer cannot know the type of each instances of an expression reference.</span></span> <span data-ttu-id="3dba7-166">Lorsque vous ajoutez un membre à la liste rouge, vous refusez tous les membres de ce nom parmi tous les types dans la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-166">When you add a member to the block list, you are denying all members of that name across all types in the allow list.</span></span>  
  
 <span data-ttu-id="3dba7-167">Les résultats d'expression RDL sont vérifiés au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="3dba7-167">RDL expression results are verified at run time.</span></span> <span data-ttu-id="3dba7-168">Les expressions RDL sont vérifiées dans la définition de rapport lorsque le rapport est publié.</span><span class="sxs-lookup"><span data-stu-id="3dba7-168">RDL expressions are verified in the report definition when the report is published.</span></span> <span data-ttu-id="3dba7-169">Contrôlez le journal des traces du serveur de rapports afin de détecter toute violation.</span><span class="sxs-lookup"><span data-stu-id="3dba7-169">Monitor the report server trace log for violations.</span></span> <span data-ttu-id="3dba7-170">Pour plus d’informations, consultez [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="3dba7-170">For more information, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
### <a name="working-with-types"></a><span data-ttu-id="3dba7-171">Utilisation des types</span><span class="sxs-lookup"><span data-stu-id="3dba7-171">Working with Types</span></span>  
 <span data-ttu-id="3dba7-172">Lorsque vous ajoutez un type à la liste verte, vous contrôlez les points d'entrée suivants pour accéder aux expressions RDL :</span><span class="sxs-lookup"><span data-stu-id="3dba7-172">When you add a type to the allow list, you are controlling the following entry points to access RDL expressions:</span></span>  
  
-   <span data-ttu-id="3dba7-173">Membres statiques d'un type.</span><span class="sxs-lookup"><span data-stu-id="3dba7-173">Static members of a type.</span></span>  
  
-   <span data-ttu-id="3dba7-174">[!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` Méthode.</span><span class="sxs-lookup"><span data-stu-id="3dba7-174">The [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` method.</span></span>  
  
-   <span data-ttu-id="3dba7-175">**\<Classes>** Élément dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="3dba7-175">The **\<Classes>** element in the report definition.</span></span>  
  
-   <span data-ttu-id="3dba7-176">Membres que vous avez ajoutés à la liste rouge pour un type dans la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-176">Members that you have added to the block list for a type in the allow list.</span></span>  
  
 <span data-ttu-id="3dba7-177">La liste verte ne contrôle pas les points d'entrée suivants :</span><span class="sxs-lookup"><span data-stu-id="3dba7-177">The allow list does not control the following entry points:</span></span>  
  
-   <span data-ttu-id="3dba7-178">Datasets du rapport.</span><span class="sxs-lookup"><span data-stu-id="3dba7-178">Report datasets.</span></span> <span data-ttu-id="3dba7-179">Les champs dans les datasets de rapport retournés à partir de requêtes peuvent contenir tout type RDL valide.</span><span class="sxs-lookup"><span data-stu-id="3dba7-179">Fields in report datasets that are returned from queries might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="3dba7-180">des paramètres de rapport ;</span><span class="sxs-lookup"><span data-stu-id="3dba7-180">Report parameters.</span></span> <span data-ttu-id="3dba7-181">Les valeurs de paramètres fournies par l'utilisateur peuvent contenir tout type RDL valide.</span><span class="sxs-lookup"><span data-stu-id="3dba7-181">User-supplied parameter values might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="3dba7-182">Membres d'un type actif qui ne sont pas dans la liste rouge.</span><span class="sxs-lookup"><span data-stu-id="3dba7-182">Members of an enabled type that are not in the block list.</span></span> <span data-ttu-id="3dba7-183">Par défaut, tous les membres de tous les types dans la liste verte sont activés.</span><span class="sxs-lookup"><span data-stu-id="3dba7-183">By default, all members of all types in the allow list are enabled.</span></span> <span data-ttu-id="3dba7-184">Lorsque vous ajoutez un nom de membre à la liste rouge, vous refusez tous les membres avec ce nom parmi tous les types figurant dans la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-184">When you add a member name to the block list, you are denying all members with that name across all types that are in the allow list.</span></span>  
  
 <span data-ttu-id="3dba7-185">Pour activer un membre d'un type mais refuser un membre avec le même nom pour un type différent, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3dba7-185">To enable a member of one type but deny a member with the same name for a different type, you must do the following:</span></span>  
  
-   <span data-ttu-id="3dba7-186">Ajoutez un **\<Deny>** élément pour le nom de membre.</span><span class="sxs-lookup"><span data-stu-id="3dba7-186">Add a **\<Deny>** element for the member name.</span></span>  
  
-   <span data-ttu-id="3dba7-187">Créer un membre de proxy avec un nom différent sur une classe dans un assembly personnalisé pour le membre que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="3dba7-187">Create a proxy member with a different name on a class in a custom assembly for the member that you want to enable.</span></span>  
  
-   <span data-ttu-id="3dba7-188">Ajouter cette classe nouvelle à la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-188">Add that new class to the allow list.</span></span>  
  
 <span data-ttu-id="3dba7-189">Pour ajouter des fonctions [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework à la liste autorisée, ajoutez les types correspondants de l’espace de noms Microsoft.VisualBasic à cette liste.</span><span class="sxs-lookup"><span data-stu-id="3dba7-189">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework functions to the allow list, add the corresponding types from the Microsoft.VisualBasic namespace to the allow list.</span></span>  
  
 <span data-ttu-id="3dba7-190">Pour ajouter des mots clés du type [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework à la liste verte, ajoutez le type CLR correspondant à la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-190">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework type keywords to the allow list, add the corresponding CLR type to the allow list.</span></span> <span data-ttu-id="3dba7-191">Par exemple, pour utiliser le [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] mot clé .NET Framework `Integer` , ajoutez le fragment XML suivant à l' **\<RDLSandboxing>** élément :</span><span class="sxs-lookup"><span data-stu-id="3dba7-191">For example, to use the [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework keyword `Integer`, add the following XML fragment to the **\<RDLSandboxing>** element:</span></span>  
  
```  
<Allow Namespace="System">Int32</Allow>  
```  
  
 <span data-ttu-id="3dba7-192">Pour ajouter un type générique ou un type nullable [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework à la liste autorisée, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="3dba7-192">To add a generic or a [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type to the allow list, you must do the following:</span></span>  
  
-   <span data-ttu-id="3dba7-193">Créer un type de proxy pour le type nullable générique ou [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3dba7-193">Create a proxy type for the generic or [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type.</span></span>  
  
-   <span data-ttu-id="3dba7-194">Ajouter le type de proxy à la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-194">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="3dba7-195">L'ajout d'un type d'un assembly personnalisé à la liste verte n'accorde pas implicitement l'autorisation Exécuter sur l'assembly.</span><span class="sxs-lookup"><span data-stu-id="3dba7-195">Adding a type from a custom assembly to the allow list does not implicitly grant execute permission on the assembly.</span></span> <span data-ttu-id="3dba7-196">Vous devez modifier spécifiquement le fichier de sécurité d'accès du code et fournir l'autorisation Exécuter à votre assembly.</span><span class="sxs-lookup"><span data-stu-id="3dba7-196">You must specifically modify the code access security file and provide execute permission to your assembly.</span></span> <span data-ttu-id="3dba7-197">Pour plus d’informations, consultez [Sécurité d’accès du code dans Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3dba7-197">For more information, see [Code Access Security in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span></span>  
  
#### <a name="maintaining-the-deny-list-of-members"></a><span data-ttu-id="3dba7-198">Gestion \<Deny> de la liste des membres</span><span class="sxs-lookup"><span data-stu-id="3dba7-198">Maintaining the \<Deny> List of Members</span></span>  
 <span data-ttu-id="3dba7-199">Lorsque vous ajoutez un nouveau type à la liste verte, vous utilisez la liste suivante pour déterminer quand vous devrez peut-être mettre à jour la liste rouge de membres :</span><span class="sxs-lookup"><span data-stu-id="3dba7-199">When you add a new type to the allow list, use the following list to determine when you might have to update the block list of members:</span></span>  
  
-   <span data-ttu-id="3dba7-200">Lorsque vous mettez à jour un assembly personnalisé avec une version qui introduit de nouveaux types.</span><span class="sxs-lookup"><span data-stu-id="3dba7-200">When you update a custom assembly with a version that introduces new types.</span></span>  
  
-   <span data-ttu-id="3dba7-201">Lorsque vous ajoutez des membres aux types dans la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-201">When you add members to the types in the allow list.</span></span>  
  
-   <span data-ttu-id="3dba7-202">Quand vous mettez à jour le [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3dba7-202">When you update the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] on the report server.</span></span>  
  
-   <span data-ttu-id="3dba7-203">Lorsque vous effectuez une mise à niveau du serveur de rapports vers une version ultérieure de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3dba7-203">When you upgrade the report server to a later version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="3dba7-204">Lorsque vous mettez à jour un serveur de rapports pour gérer un schéma RDL ultérieur, car de nouveaux membres ont pu être ajoutés aux types RDL.</span><span class="sxs-lookup"><span data-stu-id="3dba7-204">When you update a report server to handle a later RDL schema, because new members might have been added to RDL types.</span></span>  
  
### <a name="working-with-operators-and-new"></a><span data-ttu-id="3dba7-205">Utilisation des opérateurs et de New</span><span class="sxs-lookup"><span data-stu-id="3dba7-205">Working with Operators and New</span></span>  
 <span data-ttu-id="3dba7-206">Par défaut, les opérateurs de langage [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework, à l'exception de `New`, sont toujours autorisés.</span><span class="sxs-lookup"><span data-stu-id="3dba7-206">By default, [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework language operators, except for `New`, are always allowed.</span></span> <span data-ttu-id="3dba7-207">L' `New` opérateur est contrôlé par l' `AllowNew` attribut sur l' **\<Allow>** élément.</span><span class="sxs-lookup"><span data-stu-id="3dba7-207">The `New` operator is controlled by the `AllowNew` attribute on the **\<Allow>** element.</span></span> <span data-ttu-id="3dba7-208">D’autres opérateurs de langage, tels que l’opérateur d’accesseur de collection par défaut `!` et les [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] macros de cast .NET Framework telles que `CInt` , sont toujours autorisés.</span><span class="sxs-lookup"><span data-stu-id="3dba7-208">Other language operators, such as the default collection accessor operator `!` and [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework cast macros such as `CInt`, are always allowed.</span></span>  
  
 <span data-ttu-id="3dba7-209">L'ajout d'opérateurs à une liste rouge, y compris des opérateurs personnalisés, n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="3dba7-209">Adding operators to a block list, including custom operators, is not supported.</span></span> <span data-ttu-id="3dba7-210">Pour exclure des opérateurs pour un type, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3dba7-210">To exclude operators for a type, you must do the following:</span></span>  
  
-   <span data-ttu-id="3dba7-211">Créer un type de proxy qui n'implémente pas les opérateurs que vous souhaitez exclure.</span><span class="sxs-lookup"><span data-stu-id="3dba7-211">Create a proxy type that does not implement the operators that you want to exclude.</span></span>  
  
-   <span data-ttu-id="3dba7-212">Ajouter le type de proxy à la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-212">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="3dba7-213">Pour créer un tableau dans une expression RDL, créez le tableau dans une méthode sur une classe que vous définissez et ajoutez cette classe à la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-213">To create a new array in an RDL expression, create the array in a method on a class that you define, and add that class to the allow list.</span></span>  
  
 <span data-ttu-id="3dba7-214">Pour créer un tableau dans une expression RDL, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3dba7-214">To create a new array in an RDL expression, you must do the following:</span></span>  
  
-   <span data-ttu-id="3dba7-215">Définir une nouvelle classe et créer le tableau dans une méthode sur cette classe.</span><span class="sxs-lookup"><span data-stu-id="3dba7-215">Define a new class and create the array in a method on that class.</span></span>  
  
-   <span data-ttu-id="3dba7-216">Ajouter la classe à la liste verte.</span><span class="sxs-lookup"><span data-stu-id="3dba7-216">Add the class to the allow list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dba7-217">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3dba7-217">See Also</span></span>  
 <span data-ttu-id="3dba7-218">[Fichier de configuration RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="3dba7-218">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 [<span data-ttu-id="3dba7-219">Report Server Service Trace Log</span><span class="sxs-lookup"><span data-stu-id="3dba7-219">Report Server Service Trace Log</span></span>](report-server/report-server-service-trace-log.md)  
  
  
