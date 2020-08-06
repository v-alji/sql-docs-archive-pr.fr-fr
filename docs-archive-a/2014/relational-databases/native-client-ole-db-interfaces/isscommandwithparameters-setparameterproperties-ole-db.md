---
title: ISSCommandWithParameters::SetParameterProperties (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::SetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- SetParameterProperties method
ms.assetid: 4cd0281a-a2a0-43df-8e46-eb478b64cb4b
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bf8e5cde9885a5d9b55d84c6384b76aecf50b8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696795"
---
# <a name="isscommandwithparameterssetparameterproperties-ole-db"></a><span data-ttu-id="f8027-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f8027-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="f8027-103">Définit les propriétés de paramètre pour chaque paramètre par ordinal ou définit des propriétés de paramètre en bloc en spécifiant un tableau de structures SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="f8027-103">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of SSPARAMPROPS structures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8027-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f8027-104">Syntax</span></span>  
  
```  
  
HRESULT SetParameterProperties(  
DB_UPARAMS cParams,   
SSPARAMPROPS rgParamProperties[]);  
```  
  
## <a name="arguments"></a><span data-ttu-id="f8027-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="f8027-105">Arguments</span></span>  
 <span data-ttu-id="f8027-106">*cParams*[in]</span><span class="sxs-lookup"><span data-stu-id="f8027-106">*cParams*[in]</span></span>  
 <span data-ttu-id="f8027-107">Nombre de structures SSPARAMPROPS dans le tableau *rgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="f8027-107">The number of SSPARAMPROPS structures in the *rgParamProperties* array.</span></span> <span data-ttu-id="f8027-108">Si ce nombre est égal à zéro, `ISSCommandWithParameters::SetParameterProperties` supprimera toutes les propriétés qui ont pu être spécifiées pour tous les paramètres de la commande.</span><span class="sxs-lookup"><span data-stu-id="f8027-108">If this number is zero, `ISSCommandWithParameters::SetParameterProperties` will delete all properties that might have been specified for any parameters in the command.</span></span>  
  
 <span data-ttu-id="f8027-109">*rgParamProperties*[in]</span><span class="sxs-lookup"><span data-stu-id="f8027-109">*rgParamProperties*[in]</span></span>  
 <span data-ttu-id="f8027-110">Tableau de structures SSPARAMPROPS à définir.</span><span class="sxs-lookup"><span data-stu-id="f8027-110">An array of SSPARAMPROPS structures to be set.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="f8027-111">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="f8027-111">Return Code Values</span></span>  
 <span data-ttu-id="f8027-112">La `ISSCommandWithParameters::SetParameterProperties` méthode retourne les mêmes codes d’erreur que la méthode core OLE DB **ICommandProperties :: SetProperties** .</span><span class="sxs-lookup"><span data-stu-id="f8027-112">The `ISSCommandWithParameters::SetParameterProperties` method returns the same error codes as the core OLE DB **ICommandProperties::SetProperties** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8027-113">Notes</span><span class="sxs-lookup"><span data-stu-id="f8027-113">Remarks</span></span>  
 <span data-ttu-id="f8027-114">La définition des propriétés de paramètre avec cette méthode est autorisée pour chaque paramètre par ordinal, ou à l’aide d’un `ISSCommandWithParameters::SetParameterProperties` appel unique une fois que le SSPARAMPROPS a été généré à partir du tableau de propriétés.</span><span class="sxs-lookup"><span data-stu-id="f8027-114">Setting parameter properties with this method is allowed on a per parameter basis by ordinal, or with a single `ISSCommandWithParameters::SetParameterProperties` call once the SSPARAMPROPS has been built from the property array.</span></span>  
  
 <span data-ttu-id="f8027-115">La méthode **SetParameterInfo** doit être appelée avant d’appeler la `ISSCommandWithParameters::SetParameterProperties` méthode.</span><span class="sxs-lookup"><span data-stu-id="f8027-115">The **SetParameterInfo** method must be called before calling the `ISSCommandWithParameters::SetParameterProperties` method.</span></span> <span data-ttu-id="f8027-116">Le fait d'appeler `SetParameterProperties(0, NULL)` efface toutes les propriétés de paramètre spécifiées, tandis que l'appel de `SetParameterInfo(0,NULL,NULL)` efface toutes les informations sur les paramètres y compris toutes les propriétés qui peuvent être associées à un paramètre.</span><span class="sxs-lookup"><span data-stu-id="f8027-116">Calling `SetParameterProperties(0, NULL)` clears all specified parameter properties, while calling `SetParameterInfo(0,NULL,NULL)` clears all the parameter info including any properties that might be associated with a parameter.</span></span>  
  
 <span data-ttu-id="f8027-117">`ISSCommandWithParameters::SetParameterProperties`L’appel de pour spécifier des propriétés pour un paramètre qui n’est pas de type DBTYPE_XML ou DBTYPE_UDT retourne DB_E_ERRORSOCCURRED ou DB_S_ERRORSOCCURRED, et marque le champ *dwStatus* de tous les DBPROP contenus dans SSPARAMPROPS pour ce paramètre avec DBPROPSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="f8027-117">Calling `ISSCommandWithParameters::SetParameterProperties` to specify properties for a parameter which is not of type DBTYPE_XML or DBTYPE_UDT returns DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED and marks the *dwStatus* field of all DBPROPs contained in SSPARAMPROPS for that parameter with DBPROPSTATUS_NOTSET.</span></span> <span data-ttu-id="f8027-118">Le tableau DBPROP de chaque DBPROPSET contenu dans SSPARAMPROPS doit être parcouru pour détecter le paramètre auquel DB_E_ERRORSOCCURRED ou DB_S_ERRORSOCCURRED fait référence.</span><span class="sxs-lookup"><span data-stu-id="f8027-118">The DBPROP array of each DBPROPSET contained in SSPARAMPROPS should be traversed to detect which parameter the DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED refers to.</span></span>  
  
 <span data-ttu-id="f8027-119">Si `ISSCommandWithParameters::SetParameterProperties` est appelé pour spécifier les propriétés des paramètres dont les informations sur les paramètres n’ont pas encore été définies avec **SetParameterInfo**, le fournisseur retourne E_UNEXPECTED avec le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="f8027-119">If `ISSCommandWithParameters::SetParameterProperties` is called to specify the properties of parameters whose parameter info have not been set yet with **SetParameterInfo**, the provider returns E_UNEXPECTED with the following error message:</span></span>  
  
 <span data-ttu-id="f8027-120">La méthode SetParameterProperties ne peut pas être appelée pour les paramètres spécifiés sans appeler auparavant la méthode SetParameterInfo.</span><span class="sxs-lookup"><span data-stu-id="f8027-120">SetParameterProperties method cannot be called for the specified parameters without first calling SetParameterInfo method.</span></span> <span data-ttu-id="f8027-121">Vous devez définir les informations de paramètre avant de définir les propriétés de paramètre.</span><span class="sxs-lookup"><span data-stu-id="f8027-121">The parameter information must be set before setting the parameter properties.</span></span>  
  
 <span data-ttu-id="f8027-122">Si l’appel à `ISSCommandWithParameters::SetParameterProperties` contient des paramètres où les informations sur les paramètres ont été définies et des paramètres où les informations sur les paramètres n’ont pas été définies, les propriétés dwStatus dans le DBPROPSET de la propriété SSPARAMPROPS sont retournées avec DBSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="f8027-122">If the call to `ISSCommandWithParameters::SetParameterProperties` contains some parameters where the parameter info has been set, and some parameters where the parameter info has not been set, the dwStatus properties in the DBPROPSET of the SSPARAMPROPS property set will return with DBSTATUS_NOTSET.</span></span>  
  
 <span data-ttu-id="f8027-123">La structure SSPARAMPROPS est défini comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8027-123">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
 <span data-ttu-id="f8027-124">Les améliorations apportées au moteur de base de données à compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permettent à ISSCommandWithParameters::SetParameterProperties d'obtenir des descriptions plus exactes des résultats attendus.</span><span class="sxs-lookup"><span data-stu-id="f8027-124">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ISSCommandWithParameters::SetParameterProperties to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="f8027-125">Ces résultats plus exacts peuvent différer des valeurs retournées ISSCommandWithParameters::SetParameterProperties dans les versions précédentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8027-125">These more accurate results may differ from the values returned by ISSCommandWithParameters::SetParameterProperties in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f8027-126">Pour plus d’informations, consultez [Découverte des métadonnées](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="f8027-126">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
|<span data-ttu-id="f8027-127">Membre</span><span class="sxs-lookup"><span data-stu-id="f8027-127">Member</span></span>|<span data-ttu-id="f8027-128">Description</span><span class="sxs-lookup"><span data-stu-id="f8027-128">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f8027-129">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="f8027-129">*iOrdinal*</span></span>|<span data-ttu-id="f8027-130">Position ordinale du paramètre transmis.</span><span class="sxs-lookup"><span data-stu-id="f8027-130">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="f8027-131">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="f8027-131">*cPropertySets*</span></span>|<span data-ttu-id="f8027-132">Nombre de structures DBPROPSET dans *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="f8027-132">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="f8027-133">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="f8027-133">*rgPropertySets*</span></span>|<span data-ttu-id="f8027-134">Pointeur vers la mémoire dans lequel retourner un tableau de structures DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="f8027-134">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8027-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8027-135">See Also</span></span>  
 [<span data-ttu-id="f8027-136">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f8027-136">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
