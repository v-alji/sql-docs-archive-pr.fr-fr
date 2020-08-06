---
title: Implémenter une stratégie de signature en définissant une valeur de Registre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- signing policies [Integration Services]
ms.assetid: 64f6966f-2292-401f-acb1-2ccb5aee484a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e844b65df5b45f212554f7583f4e4b327b740e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601572"
---
# <a name="implement-a-signing-policy-by-setting-a-registry-value"></a><span data-ttu-id="22655-102">Implémenter une stratégie de signature en définissant une valeur du Registre</span><span class="sxs-lookup"><span data-stu-id="22655-102">Implement a Signing Policy by Setting a Registry Value</span></span>
  <span data-ttu-id="22655-103">Vous pouvez utiliser une valeur du Registre facultative pour gérer la stratégie d'une organisation pour charger des packages signés ou non signés.</span><span class="sxs-lookup"><span data-stu-id="22655-103">You can use an optional registry value to manage an organization's policy for loading signed or unsigned packages.</span></span> <span data-ttu-id="22655-104">Si vous utilisez cette valeur du Registre, vous devez créer cette valeur du Registre sur tous les ordinateurs sur lesquels les packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] s'exécuteront et sur lesquels vous souhaitez appliquer la stratégie.</span><span class="sxs-lookup"><span data-stu-id="22655-104">If you use this registry value, you must create this registry value on each computer on which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages will run and on which you want to enforce the policy.</span></span> <span data-ttu-id="22655-105">Une fois la valeur du Registre définie, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] vérifiera les signatures avant de charger les packages.</span><span class="sxs-lookup"><span data-stu-id="22655-105">After the registry value has been set, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] will check or verify the signatures before loading packages.</span></span>  
  
 <span data-ttu-id="22655-106">La procédure décrite dans cette rubrique explique comment ajouter la valeur DWORD facultative `BlockedSignatureStates` à la clé de Registre HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span><span class="sxs-lookup"><span data-stu-id="22655-106">This procedure in this topic describes how to add the optional `BlockedSignatureStates` DWORD value to the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS registry key.</span></span> <span data-ttu-id="22655-107">La valeur de données dans `BlockedSignatureStates` détermine si un package doit être bloqué s'il possède une signature non approuvée, une signature non valide ou s'il n'est pas signé.</span><span class="sxs-lookup"><span data-stu-id="22655-107">The data value in `BlockedSignatureStates` determines whether a package should be blocked if it has an untrusted signature, has an invalid signature, or is unsigned.</span></span> <span data-ttu-id="22655-108">En ce qui concerne l'état des signatures utilisées pour signer les packages, la valeur de Registre `BlockedSignatureStates` emploie les définitions suivantes :</span><span class="sxs-lookup"><span data-stu-id="22655-108">With regard to the status of signatures used to sign packages, the `BlockedSignatureStates` registry value uses the following definitions:</span></span>  
  
-   <span data-ttu-id="22655-109">Une *signature valide* est une signature qui peut être lue correctement.</span><span class="sxs-lookup"><span data-stu-id="22655-109">A *valid signature* is one that can be read successfully.</span></span>  
  
-   <span data-ttu-id="22655-110">Une *signature non valide* est une signature dont la somme de contrôle déchiffrée (hachage unidirectionnel du code de package chiffré par une clé privée) ne correspond pas à la somme de contrôle déchiffrée calculée dans le cadre du chargement des packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22655-110">An *invalid signature* is one for which the decrypted checksum (the one-way hash of the package code encrypted by a private key) does not match the decrypted checksum that is calculated as part of the process of loading [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
-   <span data-ttu-id="22655-111">Une *signature approuvée* est une signature créée à l’aide d’un certificat numérique signé par une autorité de certification racine de confiance.</span><span class="sxs-lookup"><span data-stu-id="22655-111">A *trusted signature* is one that is created by using a digital certificate signed by a Trusted Root Certification Authority.</span></span> <span data-ttu-id="22655-112">Ce paramètre n'exige pas la recherche du signataire dans la liste Éditeurs approuvés de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="22655-112">This setting does not require the signer to be found in the user's list of Trusted Publishers.</span></span>  
  
-   <span data-ttu-id="22655-113">Une *signature non approuvée* est une signature qui ne peut pas être vérifiée en tant que signature émise par une autorité de certification racine de confiance ou bien une signature qui n’est pas actuelle.</span><span class="sxs-lookup"><span data-stu-id="22655-113">An *untrusted signature* is one that cannot be verified as issued by a Trusted Root Certification Authority, or a signature that is not current.</span></span>  
  
 <span data-ttu-id="22655-114">Le tableau suivant répertorie les valeurs valides des données DWORD et leur stratégie associée.</span><span class="sxs-lookup"><span data-stu-id="22655-114">The following table lists the valid values of the DWORD data and their associated policy.</span></span>  
  
|<span data-ttu-id="22655-115">Valeur</span><span class="sxs-lookup"><span data-stu-id="22655-115">Value</span></span>|<span data-ttu-id="22655-116">Description</span><span class="sxs-lookup"><span data-stu-id="22655-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22655-117">0</span><span class="sxs-lookup"><span data-stu-id="22655-117">0</span></span>|<span data-ttu-id="22655-118">Pas de restriction administrative.</span><span class="sxs-lookup"><span data-stu-id="22655-118">No administrative restriction.</span></span>|  
|<span data-ttu-id="22655-119">1</span><span class="sxs-lookup"><span data-stu-id="22655-119">1</span></span>|<span data-ttu-id="22655-120">Bloquer les signatures non valides.</span><span class="sxs-lookup"><span data-stu-id="22655-120">Block invalid signatures.</span></span><br /><br /> <span data-ttu-id="22655-121">Ce paramètre ne bloque pas les packages non signés.</span><span class="sxs-lookup"><span data-stu-id="22655-121">This setting does not block unsigned packages.</span></span>|  
|<span data-ttu-id="22655-122">2</span><span class="sxs-lookup"><span data-stu-id="22655-122">2</span></span>|<span data-ttu-id="22655-123">Bloquer les signatures non valides et non approuvées.</span><span class="sxs-lookup"><span data-stu-id="22655-123">Block invalid and untrusted signatures.</span></span><br /><br /> <span data-ttu-id="22655-124">Ce paramètre ne bloque pas les packages non signés mais bloque les signatures générées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="22655-124">This setting does not block unsigned packages, but blocks self-generated signatures.</span></span>|  
|<span data-ttu-id="22655-125">3</span><span class="sxs-lookup"><span data-stu-id="22655-125">3</span></span>|<span data-ttu-id="22655-126">Bloquer les signatures non valides et non approuvées et les packages non signés.</span><span class="sxs-lookup"><span data-stu-id="22655-126">Block invalid and untrusted signatures and unsigned packages</span></span><br /><br /> <span data-ttu-id="22655-127">Ce paramètre bloque lui aussi les signatures générées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="22655-127">This setting also blocks self-generated signatures.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="22655-128">Le paramètre recommandé pour `BlockedSignatureStates` est 3.</span><span class="sxs-lookup"><span data-stu-id="22655-128">The recommended setting for `BlockedSignatureStates` is 3.</span></span> <span data-ttu-id="22655-129">Ce paramètre offre une protection maximale contre des packages non signés ou des signatures non valides ou non approuvées.</span><span class="sxs-lookup"><span data-stu-id="22655-129">This setting provides the greatest protection against unsigned packages or signatures that are either not valid or untrusted.</span></span> <span data-ttu-id="22655-130">Néanmoins, ce paramètre recommandé peut ne pas convenir dans tous les cas.</span><span class="sxs-lookup"><span data-stu-id="22655-130">However, the recommended setting may not be appropriate in all circumstances.</span></span> <span data-ttu-id="22655-131">Pour plus d’informations sur la signature des ressources numériques, consultez la rubrique[Introduction to Code Signing](https://go.microsoft.com/fwlink/?LinkId=51414)(Introduction à la signature du code) dans MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="22655-131">For more information about signing digital assets, see the topic, "[Introduction to Code Signing](https://go.microsoft.com/fwlink/?LinkId=51414)," in the MSDN Library.</span></span>  
  
### <a name="to-implement-a-signing-policy-for-packages"></a><span data-ttu-id="22655-132">Pour implémenter une stratégie de signature pour des packages</span><span class="sxs-lookup"><span data-stu-id="22655-132">To implement a signing policy for packages</span></span>  
  
1.  <span data-ttu-id="22655-133">Dans le menu **Démarrer** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="22655-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="22655-134">Dans la boîte de dialogue Exécuter, tapez `Regedit` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="22655-134">In the Run dialog box, type `Regedit`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="22655-135">Localisez la clé de registre HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span><span class="sxs-lookup"><span data-stu-id="22655-135">Locate the registry key, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span></span>  
  
4.  <span data-ttu-id="22655-136">Cliquez avec le bouton droit sur **MSDTS**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD**.</span><span class="sxs-lookup"><span data-stu-id="22655-136">Right-click **MSDTS**, point to **New**, and then click **DWORD Value**.</span></span>  
  
5.  <span data-ttu-id="22655-137">Remplacez le nom de la nouvelle valeur par `BlockedSignatureStates`.</span><span class="sxs-lookup"><span data-stu-id="22655-137">Update the name of the new value to `BlockedSignatureStates`.</span></span>  
  
6.  <span data-ttu-id="22655-138">Cliquez avec le bouton droit `BlockedSignatureStates` et cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="22655-138">Right-click `BlockedSignatureStates` and click **Modify**.</span></span>  
  
7.  <span data-ttu-id="22655-139">Dans la boîte de dialogue **Édition de la valeur DWORD** , tapez la valeur 0, 1, 2 ou 3.</span><span class="sxs-lookup"><span data-stu-id="22655-139">In the **Edit DWORD Value** dialog box, type the value 0, 1, 2, or 3.</span></span>  
  
8.  <span data-ttu-id="22655-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="22655-140">Click **OK**.</span></span>  
  
9. <span data-ttu-id="22655-141">Dans le menu **Fichier** , cliquez sur **Quitter**.</span><span class="sxs-lookup"><span data-stu-id="22655-141">On the **File** menu, click **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22655-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22655-142">See Also</span></span>  
 <span data-ttu-id="22655-143">[Vue d’ensemble de la sécurité &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="22655-143">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="22655-144">Identifier la source de packages à l'aide de signatures numériques</span><span class="sxs-lookup"><span data-stu-id="22655-144">Identify the Source of Packages with Digital Signatures</span></span>](security/identify-the-source-of-packages-with-digital-signatures.md)  
  
  
