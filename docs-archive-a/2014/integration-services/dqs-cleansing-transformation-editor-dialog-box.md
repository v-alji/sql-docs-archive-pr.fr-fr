---
title: Éditeur de transformation de nettoyage DQS, boîte de dialogue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssdqs.designer.cleansing.f1
- SQL12.SSDQS.DESIGNER.DQCONNECTION.F1
ms.assetid: 07e79641-71ee-45d0-a9ba-ed6f9f68f333
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e97cd138bb17ce3cfe476496e5bc576875728224
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601014"
---
# <a name="dqs-cleansing-transformation-editor-dialog-box"></a><span data-ttu-id="00da3-102">Éditeur de transformation de nettoyage DQS (boîte de dialogue)</span><span class="sxs-lookup"><span data-stu-id="00da3-102">DQS Cleansing Transformation Editor Dialog Box</span></span>
  <span data-ttu-id="00da3-103">Utilisez la boîte de dialogue de **l’Éditeur de transformation de nettoyage DQS** pour corriger les données à l’aide de DQS (Data Quality Services).</span><span class="sxs-lookup"><span data-stu-id="00da3-103">Use the **DQS Cleansing Transformation Editor** dialog box to correct data using Data Quality Services (DQS).</span></span> <span data-ttu-id="00da3-104">Pour plus d’informations, consultez [Concepts Data Quality Services](../../2014/data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-104">For more information, see [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="00da3-105">Pour en savoir plus sur la transformation, consultez [Transformation de nettoyage DQS](data-flow/transformations/dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-105">To learn more about the transformation, see [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="00da3-106">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="00da3-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="00da3-107">Ouvrir l'Éditeur de transformation de nettoyage DQS</span><span class="sxs-lookup"><span data-stu-id="00da3-107">Open the DQS Cleansing Transformation Editor</span></span>](#open)  
  
-   [<span data-ttu-id="00da3-108">Définir les options de l’onglet Gestionnaire de connexions</span><span class="sxs-lookup"><span data-stu-id="00da3-108">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="00da3-109">Définir les options sur l'onglet mappage</span><span class="sxs-lookup"><span data-stu-id="00da3-109">Set options on the Mapping tab</span></span>](#mapping)  
  
-   [<span data-ttu-id="00da3-110">Définir les options de l'onglet Avancé</span><span class="sxs-lookup"><span data-stu-id="00da3-110">Set options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="00da3-111">Définir les options dans la boîte de dialogue Gestionnaire de connexions du nettoyage DQS</span><span class="sxs-lookup"><span data-stu-id="00da3-111">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>](#manager)  
  
##  <a name="open-the-dqs-cleansing-transformation-editor"></a><a name="open"></a><span data-ttu-id="00da3-112">Ouvrir l’éditeur de transformation de nettoyage DQS</span><span class="sxs-lookup"><span data-stu-id="00da3-112">Open the DQS Cleansing Transformation Editor</span></span>  
  
1.  <span data-ttu-id="00da3-113">Ajoutez la transformation de nettoyage DQS au package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00da3-113">Add the DQS Cleansing Transformation to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="00da3-114">Cliquez avec le bouton droit sur le composant, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="00da3-114">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a> <span data-ttu-id="00da3-115">Définir les options de l'onglet Gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="00da3-115">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="00da3-116">**Gestionnaire de connexions Data Quality Services**</span><span class="sxs-lookup"><span data-stu-id="00da3-116">**Data quality connection manager**</span></span>  
 <span data-ttu-id="00da3-117">Sélectionnez un gestionnaire de connexions DQS existant dans la liste, ou créez une connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="00da3-117">Select an existing DQS connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="00da3-118">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="00da3-118">**New**</span></span>  
 <span data-ttu-id="00da3-119">Créez un gestionnaire de connexions à l’aide de la boîte de dialogue **Gestionnaire de connexions du nettoyage DQS** .</span><span class="sxs-lookup"><span data-stu-id="00da3-119">Create a new connection manager by using the **DQS Cleansing Connection Manager** dialog box.</span></span> <span data-ttu-id="00da3-120">Consultez [Définir les options dans la boîte de dialogue Gestionnaire de connexions du nettoyage DQS](#manager)</span><span class="sxs-lookup"><span data-stu-id="00da3-120">See [Set the options in the DQS Cleansing Connection Manager dialog box](#manager)</span></span>  
  
 <span data-ttu-id="00da3-121">**Base de connaissances Data Quality Services**</span><span class="sxs-lookup"><span data-stu-id="00da3-121">**Data Quality Knowledge Base**</span></span>  
 <span data-ttu-id="00da3-122">Sélectionnez une base de connaissances DQS existante pour la source de données connectée.</span><span class="sxs-lookup"><span data-stu-id="00da3-122">Select an existing DQS knowledge base for the connected data source.</span></span> <span data-ttu-id="00da3-123">Pour plus d’informations sur la base de connaissances DQS, consultez [Bases de connaissances et domaines DQS](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-123">For more information about the DQS knowledge base, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="00da3-124">**Chiffrer la connexion**</span><span class="sxs-lookup"><span data-stu-id="00da3-124">**Encrypt connection**</span></span>  
 <span data-ttu-id="00da3-125">spécifiez s’il faut chiffrer la connexion, afin de chiffrer le transfert de données entre le serveur DQS et [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00da3-125">specify whether to encrypt the connection, in order to encrypt the data transfer between the DQS Server and [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="00da3-126">**Champs disponibles**</span><span class="sxs-lookup"><span data-stu-id="00da3-126">**Available domains**</span></span>  
 <span data-ttu-id="00da3-127">Répertorie les champs disponibles pour la base de connaissances sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="00da3-127">Lists the available domains for the selected knowledge base.</span></span> <span data-ttu-id="00da3-128">Il existe deux types de champs : domaines uniques, et domaines composés qui contiennent au moins deux domaines uniques.</span><span class="sxs-lookup"><span data-stu-id="00da3-128">There are two types of domains: single domains, and composite domains that contain two or more single domains.</span></span>  
  
 <span data-ttu-id="00da3-129">Pour plus d’informations sur la façon de mapper des colonnes à des domaines composites, consultez [Mapper des colonnes à des domaines composites](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-129">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="00da3-130">Pour plus d’informations sur les domaines, consultez [Bases de connaissances et domaines DQS](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-130">For more information about domains, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="00da3-131">**Configurer la sortie d’erreur**</span><span class="sxs-lookup"><span data-stu-id="00da3-131">**Configure Error Output**</span></span>  
 <span data-ttu-id="00da3-132">Spécifiez le mode de gestion des erreurs au niveau des lignes.</span><span class="sxs-lookup"><span data-stu-id="00da3-132">Specify how to handle row-level errors.</span></span> <span data-ttu-id="00da3-133">Des erreurs peuvent se produire lorsque la transformation corrige des données de la source de données connectée, en raison de valeurs de données ou de contraintes de validation inattendues.</span><span class="sxs-lookup"><span data-stu-id="00da3-133">Errors can occur when the transformation corrects data from the connected data source, due to unexpected data values or validation constraints.</span></span>  
  
 <span data-ttu-id="00da3-134">Les valeurs suivantes sont valides :</span><span class="sxs-lookup"><span data-stu-id="00da3-134">The following are the valid values:</span></span>  
  
-   <span data-ttu-id="00da3-135">**Composant défaillant**, qui indique que la transformation a échoué et que les données d’entrée ne sont pas insérées dans la base de données Data Quality Services.</span><span class="sxs-lookup"><span data-stu-id="00da3-135">**Fail Component**, which indicates that the transformation fails and the input data is not inserted into the Data Quality Services database.</span></span> <span data-ttu-id="00da3-136">Valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="00da3-136">This is the default value.</span></span>  
  
-   <span data-ttu-id="00da3-137">**Réacheminer la ligne**, qui indique que les données d’entrée ne sont pas insérées dans la base de données Data Quality Services et qu’elles sont redirigées vers la sortie d’erreur.</span><span class="sxs-lookup"><span data-stu-id="00da3-137">**Redirect Row**, which indicates that the input data is not inserted into the Data Quality Services database and is redirected to the error output.</span></span>  
  
##  <a name="set-options-on-the-mapping-tab"></a><a name="mapping"></a><span data-ttu-id="00da3-138">Définir les options sur l’onglet Mappage</span><span class="sxs-lookup"><span data-stu-id="00da3-138">Set options on the Mapping tab</span></span>  
 <span data-ttu-id="00da3-139">Pour plus d’informations sur la façon de mapper des colonnes à des domaines composites, consultez [Mapper des colonnes à des domaines composites](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-139">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="00da3-140">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="00da3-140">**Available Input Columns**</span></span>  
 <span data-ttu-id="00da3-141">Répertorie les colonnes à partir de la source de données connectée.</span><span class="sxs-lookup"><span data-stu-id="00da3-141">Lists the columns from the connected data source.</span></span> <span data-ttu-id="00da3-142">Sélectionnez une ou plusieurs colonnes qui contiennent les données que vous souhaitez corriger.</span><span class="sxs-lookup"><span data-stu-id="00da3-142">Select one or more columns that contain data that you want to correct.</span></span>  
  
 <span data-ttu-id="00da3-143">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="00da3-143">**Input Column**</span></span>  
 <span data-ttu-id="00da3-144">Répertorie une colonne d’entrée sélectionnée dans la zone **Colonnes d’entrée disponibles** .</span><span class="sxs-lookup"><span data-stu-id="00da3-144">Lists an input column that you selected in the **Available Input Columns** area.</span></span>  
  
 <span data-ttu-id="00da3-145">**Domaine**</span><span class="sxs-lookup"><span data-stu-id="00da3-145">**Domain**</span></span>  
 <span data-ttu-id="00da3-146">Sélectionnez un domaine pour la mapper à la colonne d'entrée.</span><span class="sxs-lookup"><span data-stu-id="00da3-146">Select a domain to map to the input column.</span></span>  
  
 <span data-ttu-id="00da3-147">**Alias source**</span><span class="sxs-lookup"><span data-stu-id="00da3-147">**Source Alias**</span></span>  
 <span data-ttu-id="00da3-148">Répertorie la colonne source qui contient la valeur de colonne d'origine.</span><span class="sxs-lookup"><span data-stu-id="00da3-148">Lists the source column that contains the original column value.</span></span>  
  
 <span data-ttu-id="00da3-149">Cliquez dans le champ pour modifier le nom de colonne.</span><span class="sxs-lookup"><span data-stu-id="00da3-149">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="00da3-150">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="00da3-150">**Output Alias**</span></span>  
 <span data-ttu-id="00da3-151">Répertorie la colonne générée par la **Transformation de nettoyage DQS**.</span><span class="sxs-lookup"><span data-stu-id="00da3-151">Lists the column that is outputted by the **DQS Cleansing Transformation**.</span></span> <span data-ttu-id="00da3-152">Cette colonne contient la valeur de colonne d'origine ou la valeur corrigée.</span><span class="sxs-lookup"><span data-stu-id="00da3-152">The column contains the original column value or the corrected value.</span></span>  
  
 <span data-ttu-id="00da3-153">Cliquez dans le champ pour modifier le nom de colonne.</span><span class="sxs-lookup"><span data-stu-id="00da3-153">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="00da3-154">**Alias d'état**</span><span class="sxs-lookup"><span data-stu-id="00da3-154">**Status Alias**</span></span>  
 <span data-ttu-id="00da3-155">Répertorie la colonne qui contient les informations d'état des données corrigées.</span><span class="sxs-lookup"><span data-stu-id="00da3-155">Lists the column that contains status information for the corrected data.</span></span> <span data-ttu-id="00da3-156">Cliquez dans le champ pour modifier le nom de colonne.</span><span class="sxs-lookup"><span data-stu-id="00da3-156">Click in the field to modify the column name.</span></span>  
  
##  <a name="set-options-on-the-advanced-tab"></a><a name="advanced"></a><span data-ttu-id="00da3-157">Définir les options de l’onglet avancé</span><span class="sxs-lookup"><span data-stu-id="00da3-157">Set options on the Advanced tab</span></span>  
 <span data-ttu-id="00da3-158">**Normaliser la sortie**</span><span class="sxs-lookup"><span data-stu-id="00da3-158">**Standardize output**</span></span>  
 <span data-ttu-id="00da3-159">Indique s'il faut retourner les données dans un format standardisé en fonction du format de sortie défini pour les domaines.</span><span class="sxs-lookup"><span data-stu-id="00da3-159">Indicate whether to output the data in the standardized format based on the output format defined for domains.</span></span> <span data-ttu-id="00da3-160">Pour plus d’informations sur le format standardisé, consultez [Nettoyage de données](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-160">For more information about standardized format, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="00da3-161">**Garantir**</span><span class="sxs-lookup"><span data-stu-id="00da3-161">**Confidence**</span></span>  
 <span data-ttu-id="00da3-162">Indique s'il faut inclure le niveau de confiance pour les données corrigées.</span><span class="sxs-lookup"><span data-stu-id="00da3-162">Indicate whether to include the confidence level for corrected data.</span></span> <span data-ttu-id="00da3-163">Le niveau de confiance indique le degré de certitude de DQS pour la correction ou la suggestion.</span><span class="sxs-lookup"><span data-stu-id="00da3-163">The confidence level indicates the extend of certainty of DQS for the correction or suggestion.</span></span> <span data-ttu-id="00da3-164">Pour plus d’informations sur les niveaux de confiance, consultez [Nettoyage de données](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-164">For more information about confidence levels, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="00da3-165">**Motif**</span><span class="sxs-lookup"><span data-stu-id="00da3-165">**Reason**</span></span>  
 <span data-ttu-id="00da3-166">Indique s'il faut inclure la raison de la correction des données.</span><span class="sxs-lookup"><span data-stu-id="00da3-166">Indicate whether to include the reason for the data correction.</span></span>  
  
 <span data-ttu-id="00da3-167">**Données ajoutées**</span><span class="sxs-lookup"><span data-stu-id="00da3-167">**Appended Data**</span></span>  
 <span data-ttu-id="00da3-168">Indique s'il faut retourner des informations supplémentaires reçues d'un fournisseur de données de référence existant.</span><span class="sxs-lookup"><span data-stu-id="00da3-168">Indicate whether to output additional data that is received from an existing reference data provider.</span></span> <span data-ttu-id="00da3-169">Pour plus d’informations, consultez [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-169">For more information, see [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span></span>  
  
 <span data-ttu-id="00da3-170">**Schéma de données ajoutées**</span><span class="sxs-lookup"><span data-stu-id="00da3-170">**Appended Data Schema**</span></span>  
 <span data-ttu-id="00da3-171">Indique s'il faut retourner le schéma de données.</span><span class="sxs-lookup"><span data-stu-id="00da3-171">Indicate whether to output the data schema.</span></span> <span data-ttu-id="00da3-172">Pour plus d’informations, consultez [attacher un domaine ou un domaine composite à des données de référence](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-172">For more information, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
##  <a name="set-the-options-in-the-dqs-cleansing-connection-manager-dialog-box"></a><a name="manager"></a><span data-ttu-id="00da3-173">Définir les options de la boîte de dialogue Gestionnaire de connexions de nettoyage DQS</span><span class="sxs-lookup"><span data-stu-id="00da3-173">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>  
 <span data-ttu-id="00da3-174">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="00da3-174">**Server name**</span></span>  
 <span data-ttu-id="00da3-175">Sélectionnez ou entrez le nom du serveur DQS auquel vous souhaitez vous connecter.</span><span class="sxs-lookup"><span data-stu-id="00da3-175">Select or type the name of the DQS server that you want to connect to.</span></span> <span data-ttu-id="00da3-176">Pour plus d’informations sur le serveur, consultez [Administration de DQS](../../2014/data-quality-services/dqs-administration.md).</span><span class="sxs-lookup"><span data-stu-id="00da3-176">For more information about the server, see [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span></span>  
  
 <span data-ttu-id="00da3-177">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="00da3-177">**Test Connection**</span></span>  
 <span data-ttu-id="00da3-178">Cliquez pour confirmer que la connexion que vous avez spécifiée fonctionne.</span><span class="sxs-lookup"><span data-stu-id="00da3-178">Click to confirm that the connection that you specified is viable.</span></span>  
  
 <span data-ttu-id="00da3-179">Vous pouvez également ouvrir la boîte de dialogue **Gestionnaire de connexions du nettoyage DQS** à partir de la zone de connexions, en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="00da3-179">You can also open the **DQS Cleansing Connection Manager** dialog box from the connections area, by doing the following:</span></span>  
  
1.  <span data-ttu-id="00da3-180">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou créez-en un nouveau.</span><span class="sxs-lookup"><span data-stu-id="00da3-180">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or create a new one.</span></span>  
  
2.  <span data-ttu-id="00da3-181">Cliquez avec le bouton droit dans la zone des connexions, cliquez sur **Nouvelle connexion**, puis cliquez sur **DQS**.</span><span class="sxs-lookup"><span data-stu-id="00da3-181">Right-click in the connections area, click **New Connection**, and then click **DQS**.</span></span>  
  
3.  <span data-ttu-id="00da3-182">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="00da3-182">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00da3-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00da3-183">See Also</span></span>  
 [<span data-ttu-id="00da3-184">Appliquer des règles de qualité des données à la source de données</span><span class="sxs-lookup"><span data-stu-id="00da3-184">Apply Data Quality Rules to Data Source</span></span>](data-flow/transformations/apply-data-quality-rules-to-data-source.md)  
  
  
