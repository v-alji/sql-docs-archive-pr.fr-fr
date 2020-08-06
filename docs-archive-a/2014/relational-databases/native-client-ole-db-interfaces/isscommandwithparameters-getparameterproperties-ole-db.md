---
title: ISSCommandWithParameters::GetParameterProperties (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::GetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetParameterProperties method
ms.assetid: 7f4cc5ea-d028-4fe5-9192-bd153ab3c26c
author: rothja
ms.author: jroth
ms.openlocfilehash: 2160c93748375a4aa3bee3d530d441182204134a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603487"
---
# <a name="isscommandwithparametersgetparameterproperties-ole-db"></a><span data-ttu-id="664ce-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="664ce-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="664ce-103">Retourne un tableau de structures de jeu de propriétés SSPARAMPROPS, avec une propriété SSPARAMPROPS définie pour chaque paramètre UDT ou XML.</span><span class="sxs-lookup"><span data-stu-id="664ce-103">Returns an array of SSPARAMPROPS property set structures, one SSPARAMPROPS property set for each UDT or XML parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="664ce-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="664ce-104">Syntax</span></span>  
  
```  
  
HRESULT GetParameterProperties(  
DB_UPARAMS *pcParams,  
SSPARAMPROPS **prgParamProperties);  
```  
  
## <a name="arguments"></a><span data-ttu-id="664ce-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="664ce-105">Arguments</span></span>  
 <span data-ttu-id="664ce-106">*pcParams*[out][in]</span><span class="sxs-lookup"><span data-stu-id="664ce-106">*pcParams*[out][in]</span></span>  
 <span data-ttu-id="664ce-107">Pointeur vers la mémoire qui contient le nombre de structures SSPARAMPROPS retournées dans *prgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="664ce-107">A pointer to memory that contains the number of SSPARAMPROPS structures returned in *prgParamProperties*.</span></span>  
  
 <span data-ttu-id="664ce-108">*prgParamProperties*[out]</span><span class="sxs-lookup"><span data-stu-id="664ce-108">*prgParamProperties*[out]</span></span>  
 <span data-ttu-id="664ce-109">Pointeur vers la mémoire dans laquelle est retourné un tableau de structures SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="664ce-109">A pointer to memory in which an array of SSPARAMPROPS structures is returned.</span></span> <span data-ttu-id="664ce-110">Le fournisseur alloue de la mémoire pour les structures et retourne l’adresse à cette mémoire ; le consommateur libère cette mémoire avec **IMalloc :: Free** lorsqu’il n’a plus besoin des structures.</span><span class="sxs-lookup"><span data-stu-id="664ce-110">The provider allocates memory for the structures and returns the address to this memory; the consumer releases this memory with **IMalloc::Free** when it no longer needs the structures.</span></span> <span data-ttu-id="664ce-111">Avant d’appeler **IMalloc :: Free** pour *prgParamProperties*, le consommateur doit également appeler **VariantClear** pour la propriété *vValue* de chaque structure DBPROP afin d’éviter une fuite de mémoire dans les cas où le variant contient un type référence (par exemple, BSTR). Si *pcParams* est égal à zéro en cas de sortie ou si une erreur autre que DB_E_ERRORSOCCURRED se produit, le fournisseur n’alloue pas de mémoire et vérifie que *prgParamProperties* est un pointeur null sur la sortie.</span><span class="sxs-lookup"><span data-stu-id="664ce-111">Before calling **IMalloc::Free** for *prgParamProperties*, the consumer must also call **VariantClear** for the *vValue* property of each DBPROP structure in order to prevent a memory leak in cases where the variant contains a reference type (such as a BSTR.) If *pcParams* is zero on output or an error other than DB_E_ERRORSOCCURRED occurs, the provider does not allocate any memory and ensures that *prgParamProperties* is a null pointer on output.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="664ce-112">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="664ce-112">Return Code Values</span></span>  
 <span data-ttu-id="664ce-113">La méthode **GetParameterProperties** retourne les mêmes codes d’erreur que la méthode Core OLE DB **ICommandProperties :: GetProperties** , sauf que DB_S_ERRORSOCCURRED et DB_E_ERRORSOCCURED ne peuvent pas être déclenchés.</span><span class="sxs-lookup"><span data-stu-id="664ce-113">The **GetParameterProperties** method returns the same error codes as the core OLE DB **ICommandProperties::GetProperties** method, except that DB_S_ERRORSOCCURRED and DB_E_ERRORSOCCURED cannot be raised.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="664ce-114">Notes</span><span class="sxs-lookup"><span data-stu-id="664ce-114">Remarks</span></span>  
 <span data-ttu-id="664ce-115">**ISSCommandWithParameters :: GetParameterProperties** se comporte de manière cohérente par rapport à **GetParameterInfo**.</span><span class="sxs-lookup"><span data-stu-id="664ce-115">**ISSCommandWithParameters::GetParameterProperties** behaves consistently with respect to **GetParameterInfo**.</span></span> <span data-ttu-id="664ce-116">Si [ISSCommandWithParameters :: SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) ou **SetParameterInfo** n’ont pas été appelés ou ont été appelés avec cParams égal à zéro, **GetParameterInfo** dérive les informations de paramètre et retourne This.</span><span class="sxs-lookup"><span data-stu-id="664ce-116">If [ISSCommandWithParameters::SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) or **SetParameterInfo** have not been called or have been called with cParams equal to zero, **GetParameterInfo** derives parameter information and returns this.</span></span> <span data-ttu-id="664ce-117">Si **ISSCommandWithParameters :: SetParameterProperties** ou **SetParameterInfo** ont été appelés pour au moins un paramètre, **ISSCommandWithParameters :: GetParameterProperties** retourne les propriétés uniquement pour les paramètres pour lesquels **ISSCommandWithParameters :: SetParameterProperties** a été appelé.</span><span class="sxs-lookup"><span data-stu-id="664ce-117">If **ISSCommandWithParameters::SetParameterProperties** or **SetParameterInfo** have been called for at least one parameter, **ISSCommandWithParameters::GetParameterProperties** returns properties only for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span> <span data-ttu-id="664ce-118">Si **ISSCommandWithParameters :: SetParameterProperties** est appelé après **ISSCommandWithParameters :: GetParameterProperties** ou **GetParameterInfo**, les appels suivants à **ISSCommandWithParameters :: GetParameterProperties** retournent les valeurs substituées pour les paramètres pour lesquels **ISSCommandWithParameters :: SetParameterProperties** a été appelé.</span><span class="sxs-lookup"><span data-stu-id="664ce-118">If **ISSCommandWithParameters::SetParameterProperties** is called after **ISSCommandWithParameters::GetParameterProperties** or **GetParameterInfo**, subsequent calls to **ISSCommandWithParameters::GetParameterProperties** return the overridden values for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span>  
  
 <span data-ttu-id="664ce-119">La structure SSPARAMPROPS est défini comme suit :</span><span class="sxs-lookup"><span data-stu-id="664ce-119">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
|<span data-ttu-id="664ce-120">Membre</span><span class="sxs-lookup"><span data-stu-id="664ce-120">Member</span></span>|<span data-ttu-id="664ce-121">Description</span><span class="sxs-lookup"><span data-stu-id="664ce-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="664ce-122">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="664ce-122">*iOrdinal*</span></span>|<span data-ttu-id="664ce-123">Position ordinale du paramètre transmis.</span><span class="sxs-lookup"><span data-stu-id="664ce-123">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="664ce-124">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="664ce-124">*cPropertySets*</span></span>|<span data-ttu-id="664ce-125">Nombre de structures DBPROPSET dans *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="664ce-125">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="664ce-126">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="664ce-126">*rgPropertySets*</span></span>|<span data-ttu-id="664ce-127">Pointeur vers la mémoire dans lequel retourner un tableau de structures DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="664ce-127">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="664ce-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="664ce-128">See Also</span></span>  
 [<span data-ttu-id="664ce-129">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="664ce-129">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
