---
title: Interface IMDEmbedded | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 9dba8c68-4bef-4c2b-815c-c286f1a1939b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 331f8c33f7748e6591acd6d6ecda7a03ef7d8137
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603682"
---
# <a name="imdembedded-interface"></a><span data-ttu-id="c1201-102">Interface IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="c1201-102">IMDEmbedded Interface</span></span>
  <span data-ttu-id="c1201-103">L'interface IMDEmbedded est une interface publique utilisée pour gérer une base de données incorporée PowerPivot ou une base de données model tabulaire.</span><span class="sxs-lookup"><span data-stu-id="c1201-103">The IMDEmbedded interface is a public interface used to manage an embedded PowerPivot database or a tabular model database.</span></span> <span data-ttu-id="c1201-104">L'interface hérite de l'interface `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c1201-104">The interface inherits from the `IPersistStream` interface.</span></span> <span data-ttu-id="c1201-105">Elle permet les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1201-105">The interface allows for the following operations:</span></span>  
  
-   <span data-ttu-id="c1201-106">Ajouter un identificateur au flux de données incorporé dans le document conteneur.</span><span class="sxs-lookup"><span data-stu-id="c1201-106">Get an identifier to the embedded stream in the container document.</span></span>  
  
-   <span data-ttu-id="c1201-107">Définir l'URL du document contenant.</span><span class="sxs-lookup"><span data-stu-id="c1201-107">Set the URL of the containing document.</span></span>  
  
-   <span data-ttu-id="c1201-108">Définit un indicateur pour indiquer si l'application d'incorporation est dans un environnement hébergé.</span><span class="sxs-lookup"><span data-stu-id="c1201-108">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
-   <span data-ttu-id="c1201-109">Définit le chemin d'accès aux fichiers temporaires utilisés par l'application d'incorporation.</span><span class="sxs-lookup"><span data-stu-id="c1201-109">Set the path to temporary files used by the embedding application.</span></span>  
  
-   <span data-ttu-id="c1201-110">Annuler l'opération incorporée actuelle.</span><span class="sxs-lookup"><span data-stu-id="c1201-110">Cancel the current embedded operation.</span></span>  
  
-   <span data-ttu-id="c1201-111">Obtenir la taille estimée (en octets) du flux de données pour enregistrer l'objet incorporé.</span><span class="sxs-lookup"><span data-stu-id="c1201-111">Get the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="c1201-112">Hérité de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c1201-112">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="c1201-113">Vérifier si la base de données incorporée a changé depuis le dernier enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c1201-113">Verify if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="c1201-114">Hérité de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c1201-114">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="c1201-115">Charger la base de données incorporée dans le moteur local ou in-process.</span><span class="sxs-lookup"><span data-stu-id="c1201-115">Load the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="c1201-116">Hérité de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c1201-116">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="c1201-117">Enregistrer la base de données locale ou in-process sur le flux de données incorporé dans le document conteneur.</span><span class="sxs-lookup"><span data-stu-id="c1201-117">Save the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="c1201-118">Hérité de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c1201-118">Inherited from `IPersistStream`.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c1201-119">Informations de référence</span><span class="sxs-lookup"><span data-stu-id="c1201-119">Reference</span></span>  
 <span data-ttu-id="c1201-120">La référence suivante documente l' `IMDEmbedded` interface comme présenté dans le fichier d’en-tête **Msmd. h** .</span><span class="sxs-lookup"><span data-stu-id="c1201-120">The following reference documents the `IMDEmbedded` interface as presented in **msmd.h** header file.</span></span>  
  
### <a name="source-file-pxoembeddeddataidl"></a><span data-ttu-id="c1201-121">Fichier source : PXOEmbeddedData.idl</span><span class="sxs-lookup"><span data-stu-id="c1201-121">Source file: PXOEmbeddedData.idl</span></span>  
  
```  
[  
  local,                            
  object,                           
  uuid(6B6691CF-5453-41c2-ADD9-4F320B7FD421),                       
  pointer_default(unique)           
]  
interface IMDEmbeddedData : IPersistStream  
{  
 [id(1), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in] BOOL in_fIsHosted);  
  
 [id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
  
 [id(3), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
  
 [id(4), helpstring("Set the path used by the embedding application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
  
 [id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
};  
```  
  
### <a name="imdembeddeddatagetstreamidentifier"></a><span data-ttu-id="c1201-122">IMDEmbeddedData::GetStreamIdentifier</span><span class="sxs-lookup"><span data-stu-id="c1201-122">IMDEmbeddedData::GetStreamIdentifier</span></span>  
  
```  
HRESULT GetStreamIdentifier (  
    [out, retval] BSTR * out_pbstrStreamId  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c1201-123">Description</span><span class="sxs-lookup"><span data-stu-id="c1201-123">Description</span></span>  
 <span data-ttu-id="c1201-124">Ajoute l'identificateur utilisé par l'application hôte au flux de données incorporé dans le document conteneur.</span><span class="sxs-lookup"><span data-stu-id="c1201-124">Gets the identifier used by the host application to the embedded stream in the container document.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c1201-125">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1201-125">Parameters</span></span>  
 <span data-ttu-id="c1201-126">*out_pbstrStreamId*</span><span class="sxs-lookup"><span data-stu-id="c1201-126">*out_pbstrStreamId*</span></span>  
 <span data-ttu-id="c1201-127">Spécifie l'emplacement de l'identificateur de flux de données.</span><span class="sxs-lookup"><span data-stu-id="c1201-127">Specifies the location of the stream identifier.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c1201-128">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c1201-128">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c1201-129">L'identificateur de flux de données a été retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="c1201-129">The stream identifier was successfully returned.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="c1201-130">Il n'y a aucun identificateur de flux de données.</span><span class="sxs-lookup"><span data-stu-id="c1201-130">There is no stream identifier.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c1201-131">Une erreur s'est produite lors de l'accès à l'identificateur de flux de données.</span><span class="sxs-lookup"><span data-stu-id="c1201-131">An error occurred accessing the stream identifier.</span></span>  
  
#### <a name="remarks"></a><span data-ttu-id="c1201-132">Notes</span><span class="sxs-lookup"><span data-stu-id="c1201-132">Remarks</span></span>  
 <span data-ttu-id="c1201-133">Pour vérifier si la connexion actuelle contient une base de données incorporée, l'utilisateur doit vérifier la valeur de la propriété DBPROP_MSMD_EMBEDDED_DATA depuis les propriétés de connexion OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c1201-133">To verify if the current connection contains an embedded database, the user should check the value of the DBPROP_MSMD_EMBEDDED_DATA property from the OLE DB connection properties.</span></span>  
  
 <span data-ttu-id="c1201-134">Les valeurs possibles pour DBPROP_MSMD_EMBEDDED_DATA sont :</span><span class="sxs-lookup"><span data-stu-id="c1201-134">The possible values for DBPROP_MSMD_EMBEDDED_DATA are:</span></span>  
  
|<span data-ttu-id="c1201-135">Nom</span><span class="sxs-lookup"><span data-stu-id="c1201-135">Name</span></span>|<span data-ttu-id="c1201-136">Valeur</span><span class="sxs-lookup"><span data-stu-id="c1201-136">Value</span></span>|<span data-ttu-id="c1201-137">Définition</span><span class="sxs-lookup"><span data-stu-id="c1201-137">Definition</span></span>|  
|----------|-----------|----------------|  
|<span data-ttu-id="c1201-138">DBPROPVAL_EMBED_NONE</span><span class="sxs-lookup"><span data-stu-id="c1201-138">DBPROPVAL_EMBED_NONE</span></span>|<span data-ttu-id="c1201-139">0x00</span><span class="sxs-lookup"><span data-stu-id="c1201-139">0x00</span></span>|<span data-ttu-id="c1201-140">Aucune base de données incorporée disponible</span><span class="sxs-lookup"><span data-stu-id="c1201-140">No embedded database available</span></span>|  
|<span data-ttu-id="c1201-141">DBPROPVAL_EMBED_EMBEDDED</span><span class="sxs-lookup"><span data-stu-id="c1201-141">DBPROPVAL_EMBED_EMBEDDED</span></span>|<span data-ttu-id="c1201-142">0x01</span><span class="sxs-lookup"><span data-stu-id="c1201-142">0x01</span></span>|<span data-ttu-id="c1201-143">L'application actuelle contient la base de données incorporée</span><span class="sxs-lookup"><span data-stu-id="c1201-143">The current application contains the embedded database</span></span>|  
|<span data-ttu-id="c1201-144">DBPROPVAL_EMBED_LINKED</span><span class="sxs-lookup"><span data-stu-id="c1201-144">DBPROPVAL_EMBED_LINKED</span></span>|<span data-ttu-id="c1201-145">0x02</span><span class="sxs-lookup"><span data-stu-id="c1201-145">0x02</span></span>|<span data-ttu-id="c1201-146">La base de données incorporée est hébergée dans une application distante (c.-à-d. SharePoint Server)</span><span class="sxs-lookup"><span data-stu-id="c1201-146">The embedded database is hosted in a remote application (i.e. SharePoint Server)</span></span>|  
  
#### <a name="source"></a><span data-ttu-id="c1201-147">Source</span><span class="sxs-lookup"><span data-stu-id="c1201-147">Source</span></span>  
  
```  
[id(1), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
```  
  
### <a name="imdembeddeddatasetcontainerurl"></a><span data-ttu-id="c1201-148">IMDEmbeddedData::SetContainerURL</span><span class="sxs-lookup"><span data-stu-id="c1201-148">IMDEmbeddedData::SetContainerURL</span></span>  
  
```  
HRESULT SetContainerURL (  
    [in] BSTR in_bstrURL  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c1201-149">Description</span><span class="sxs-lookup"><span data-stu-id="c1201-149">Description</span></span>  
 <span data-ttu-id="c1201-150">Définit l'URL pour le fichier qui contient le flux de données incorporé.</span><span class="sxs-lookup"><span data-stu-id="c1201-150">Sets the URL for the file containing the embedded stream.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c1201-151">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1201-151">Parameters</span></span>  
 <span data-ttu-id="c1201-152">*in_bstrURL*</span><span class="sxs-lookup"><span data-stu-id="c1201-152">*in_bstrURL*</span></span>  
 <span data-ttu-id="c1201-153">Spécifie l'URL pour le document contenant.</span><span class="sxs-lookup"><span data-stu-id="c1201-153">Specifies the URL for the containing document.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c1201-154">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c1201-154">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c1201-155">L'URL du conteneur a été définie avec succès.</span><span class="sxs-lookup"><span data-stu-id="c1201-155">The container URL was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c1201-156">Une erreur s'est produite lors de la définition de l'URL de conteneur.</span><span class="sxs-lookup"><span data-stu-id="c1201-156">An error occurred while setting the container URL.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="c1201-157">Source</span><span class="sxs-lookup"><span data-stu-id="c1201-157">Source</span></span>  
  
```  
[id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
```  
  
### <a name="imdembeddeddatasethosted"></a><span data-ttu-id="c1201-158">IMDEmbeddedData::SetHosted</span><span class="sxs-lookup"><span data-stu-id="c1201-158">IMDEmbeddedData::SetHosted</span></span>  
  
```  
HRESULT SetHosted (  
    [in] BOOL in_fIsHosted  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c1201-159">Description</span><span class="sxs-lookup"><span data-stu-id="c1201-159">Description</span></span>  
 <span data-ttu-id="c1201-160">Définit un indicateur pour indiquer si l'application d'incorporation est dans un environnement hébergé.</span><span class="sxs-lookup"><span data-stu-id="c1201-160">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c1201-161">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1201-161">Parameters</span></span>  
 <span data-ttu-id="c1201-162">*in_ftHosted*</span><span class="sxs-lookup"><span data-stu-id="c1201-162">*in_ftHosted*</span></span>  
 <span data-ttu-id="c1201-163">TRUE si l'appelant est hébergé dans une application de service (comme IIS).</span><span class="sxs-lookup"><span data-stu-id="c1201-163">TRUE if caller is in a hosted in a service application (like IIS).</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c1201-164">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c1201-164">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c1201-165">L'indicateur a été défini avec succès.</span><span class="sxs-lookup"><span data-stu-id="c1201-165">The flag was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c1201-166">Une erreur s'est produite lors de la définition de l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="c1201-166">An error occurred while setting the flag.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="c1201-167">Source</span><span class="sxs-lookup"><span data-stu-id="c1201-167">Source</span></span>  
  
```  
[id(5), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in]  BOOL in_fIsHosted);  
```  
  
### <a name="imdembeddeddatasettempdirpath"></a><span data-ttu-id="c1201-168">IMDEmbeddedData::SetTempDirPath</span><span class="sxs-lookup"><span data-stu-id="c1201-168">IMDEmbeddedData::SetTempDirPath</span></span>  
  
```  
HRESULT SetTempDirPath (  
    [in] BSTR in_bstrPath  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c1201-169">Description</span><span class="sxs-lookup"><span data-stu-id="c1201-169">Description</span></span>  
 <span data-ttu-id="c1201-170">Définit le chemin d'accès aux fichiers temporaires utilisés par l'application d'incorporation.</span><span class="sxs-lookup"><span data-stu-id="c1201-170">Set the path to temporary files used by the embedding application.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c1201-171">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1201-171">Parameters</span></span>  
 <span data-ttu-id="c1201-172">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="c1201-172">*in_bstrPath*</span></span>  
 <span data-ttu-id="c1201-173">Chemin d'accès utilisé par l'application hôte pour les fichiers temporaires.</span><span class="sxs-lookup"><span data-stu-id="c1201-173">The path used by the host application for temporary files.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c1201-174">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c1201-174">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c1201-175">Le répertoire de fichier temporaire a été défini avec succès.</span><span class="sxs-lookup"><span data-stu-id="c1201-175">The temporary file directory was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c1201-176">Une erreur s'est produite lors de la définition du chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="c1201-176">An error occurred while setting the path.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="c1201-177">Source</span><span class="sxs-lookup"><span data-stu-id="c1201-177">Source</span></span>  
  
```  
[id(4), helpstring("Set the path used by the host application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
```  
  
### <a name="imdembeddeddatacancel"></a><span data-ttu-id="c1201-178">IMDEmbeddedData::Cancel</span><span class="sxs-lookup"><span data-stu-id="c1201-178">IMDEmbeddedData::Cancel</span></span>  
  
```  
HRESULT Cancel ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="c1201-179">Description</span><span class="sxs-lookup"><span data-stu-id="c1201-179">Description</span></span>  
 <span data-ttu-id="c1201-180">Annule l'opération de base de données incorporée actuelle</span><span class="sxs-lookup"><span data-stu-id="c1201-180">Cancels the current embedded database operation</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c1201-181">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1201-181">Parameters</span></span>  
 <span data-ttu-id="c1201-182">Aucun.</span><span class="sxs-lookup"><span data-stu-id="c1201-182">None.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c1201-183">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c1201-183">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c1201-184">L'opération a été annulée avec succès.</span><span class="sxs-lookup"><span data-stu-id="c1201-184">The operation was successfully cancelled.</span></span>  
  
 `DB_E_CANTCANCEL`  
 <span data-ttu-id="c1201-185">Aucune opération annulable n'est actuellement en cours.</span><span class="sxs-lookup"><span data-stu-id="c1201-185">No cancellable operation is currently in progress.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c1201-186">Une erreur s'est produite lors de l'annulation de l'opération incorporée.</span><span class="sxs-lookup"><span data-stu-id="c1201-186">An error occurred while cancelling the embedded operation.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="c1201-187">Source</span><span class="sxs-lookup"><span data-stu-id="c1201-187">Source</span></span>  
  
```  
[id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
```  
  
### <a name="imdembeddeddatagetsizemax-ipersiststreamgetsizemax"></a><span data-ttu-id="c1201-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span><span class="sxs-lookup"><span data-stu-id="c1201-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span></span>  
  
```  
HRESULT GetSizeMax (  
    [out] ULARGE_INTEGER * out_pcbSize  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c1201-189">Description</span><span class="sxs-lookup"><span data-stu-id="c1201-189">Description</span></span>  
 <span data-ttu-id="c1201-190">Obtient la taille estimée (en octets) du flux de données pour enregistrer l'objet incorporé.</span><span class="sxs-lookup"><span data-stu-id="c1201-190">Gets the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="c1201-191">Hérité de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c1201-191">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c1201-192">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1201-192">Parameters</span></span>  
 <span data-ttu-id="c1201-193">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="c1201-193">*in_bstrPath*</span></span>  
 <span data-ttu-id="c1201-194">Taille estimée (en octets) de l'image de la base de données incorporée.</span><span class="sxs-lookup"><span data-stu-id="c1201-194">The estimated size (in bytes) of the embedded database image.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c1201-195">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c1201-195">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c1201-196">La taille a été obtenue avec succès.</span><span class="sxs-lookup"><span data-stu-id="c1201-196">The size was successfully obtained.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c1201-197">Une erreur s'est produite lors de l'obtention de la taille.</span><span class="sxs-lookup"><span data-stu-id="c1201-197">An error occurred while obtaining the size.</span></span>  
  
### <a name="imdembeddeddataisdirty-ipersiststreamisdirty"></a><span data-ttu-id="c1201-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span><span class="sxs-lookup"><span data-stu-id="c1201-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span></span>  
  
```  
HRESULT IsDirty ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="c1201-199">Description</span><span class="sxs-lookup"><span data-stu-id="c1201-199">Description</span></span>  
 <span data-ttu-id="c1201-200">Vérifie si la base de données incorporée a changé depuis le dernier enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c1201-200">Verifies if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="c1201-201">Hérité de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c1201-201">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c1201-202">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1201-202">Parameters</span></span>  
 <span data-ttu-id="c1201-203">aucun</span><span class="sxs-lookup"><span data-stu-id="c1201-203">none</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="c1201-204">Valeur(s) de retour</span><span class="sxs-lookup"><span data-stu-id="c1201-204">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="c1201-205">La base de données a changé depuis le dernier enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c1201-205">The database has changed since it was last saved.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="c1201-206">La base de données n'a pas changé depuis le dernier enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c1201-206">The database has not changed since it was last saved.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c1201-207">Une erreur s'est produite lors de l'obtention de l'état de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c1201-207">An error occurred while obtaining the database state.</span></span>  
  
### <a name="imdembeddeddataload-ipersiststreamload"></a><span data-ttu-id="c1201-208">IMDEmbeddedData::Load (IPersistStream::Load)</span><span class="sxs-lookup"><span data-stu-id="c1201-208">IMDEmbeddedData::Load (IPersistStream::Load)</span></span>  
  
```  
HRESULT Load (   
    [in] IStream * in_pStm   
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c1201-209">Description</span><span class="sxs-lookup"><span data-stu-id="c1201-209">Description</span></span>  
 <span data-ttu-id="c1201-210">Charge la base de données incorporée dans le moteur local ou in-process.</span><span class="sxs-lookup"><span data-stu-id="c1201-210">Loads the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="c1201-211">Hérité de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c1201-211">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c1201-212">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1201-212">Parameters</span></span>  
 <span data-ttu-id="c1201-213">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="c1201-213">*in_pStm*</span></span>  
 <span data-ttu-id="c1201-214">Pointeur vers une interface de flux de données à partir de laquelle charger la base de données incorporée.</span><span class="sxs-lookup"><span data-stu-id="c1201-214">A pointer to a stream interface from where to load the embedded database.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="c1201-215">Valeur(s) de retour</span><span class="sxs-lookup"><span data-stu-id="c1201-215">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="c1201-216">La base de données a été chargée avec succès.</span><span class="sxs-lookup"><span data-stu-id="c1201-216">The database was successfully loaded.</span></span>  
  
 `E_OUTOFMEMORY`  
 <span data-ttu-id="c1201-217">Pas assez de mémoire pour charger la base de données.</span><span class="sxs-lookup"><span data-stu-id="c1201-217">Not enough memory to load the database.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c1201-218">Une erreur s'est produite lors du chargement de la base de données, autre que `E_OUTOFMEMORY`.</span><span class="sxs-lookup"><span data-stu-id="c1201-218">An error occurred while loading the database, different than `E_OUTOFMEMORY`.</span></span>  
  
### <a name="imdembeddeddatasave-ipersiststreamsave"></a><span data-ttu-id="c1201-219">IMDEmbeddedData::Save (IPersistStream::Save)</span><span class="sxs-lookup"><span data-stu-id="c1201-219">IMDEmbeddedData::Save (IPersistStream::Save)</span></span>  
  
```  
HRESULT Save (   
    [in] IStream * in_pStm,  
    [in] BOOL in_fClearDirty  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c1201-220">Description</span><span class="sxs-lookup"><span data-stu-id="c1201-220">Description</span></span>  
 <span data-ttu-id="c1201-221">Enregistre la base de données locale ou in-process sur le flux de données incorporé dans le document conteneur.</span><span class="sxs-lookup"><span data-stu-id="c1201-221">Saves the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="c1201-222">Hérité de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c1201-222">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c1201-223">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1201-223">Parameters</span></span>  
 <span data-ttu-id="c1201-224">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="c1201-224">*in_pStm*</span></span>  
 <span data-ttu-id="c1201-225">Pointeur vers une interface de flux de données où enregistrer la base de données incorporée.</span><span class="sxs-lookup"><span data-stu-id="c1201-225">A pointer to a stream interface to where to save the embedded database.</span></span>  
  
 <span data-ttu-id="c1201-226">*in_fClearDirty*</span><span class="sxs-lookup"><span data-stu-id="c1201-226">*in_fClearDirty*</span></span>  
 <span data-ttu-id="c1201-227">Indicateur qui indique si l'indicateur de changement doit être effacé après cette opération.</span><span class="sxs-lookup"><span data-stu-id="c1201-227">A flag that indicates whether the dirty flag should be cleared after this operation.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="c1201-228">Valeur(s) de retour</span><span class="sxs-lookup"><span data-stu-id="c1201-228">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="c1201-229">La base de données a été enregistrée avec succès.</span><span class="sxs-lookup"><span data-stu-id="c1201-229">The database was successfully saved.</span></span>  
  
 `STG_E_CANTSAVE`  
 <span data-ttu-id="c1201-230">Une erreur s'est produite lors de l'enregistrement de la base de données, autre que `STG_E_MEDIUMFULL`.</span><span class="sxs-lookup"><span data-stu-id="c1201-230">An error occurred while saving the database, different than `STG_E_MEDIUMFULL`.</span></span>  
  
 `STG_E_MEDIUMFULL`  
 <span data-ttu-id="c1201-231">La base de données n'a pas pu être enregistrée parce qu'il n'y a plus d'espace disponible dans le périphérique de stockage.</span><span class="sxs-lookup"><span data-stu-id="c1201-231">The database could not be saved because there is no space left on the storage device.</span></span>  
  
  
