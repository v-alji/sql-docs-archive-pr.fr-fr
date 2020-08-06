---
title: Signer un package à l’aide d’un certificat numérique | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- digital signatures [Integration Services]
- signing packages [Integration Services]
- signatures [Integration Services]
ms.assetid: 182b115e-0fe2-4717-8dff-183f9eb6e397
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bd0f73d609623f882e474c96a01cd3bc0274b6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709719"
---
# <a name="sign-a-package-by-using-a-digital-certificate"></a><span data-ttu-id="adfdb-102">Signer un package à l'aide d'un certificat numérique</span><span class="sxs-lookup"><span data-stu-id="adfdb-102">Sign a Package by Using a Digital Certificate</span></span>
  <span data-ttu-id="adfdb-103">Cette rubrique décrit comment signer un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] à l'aide d'un certificat numérique.</span><span class="sxs-lookup"><span data-stu-id="adfdb-103">This topic describes how to sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package with a digital certificate.</span></span> <span data-ttu-id="adfdb-104">Vous pouvez utiliser une signature numérique avec d'autres paramètres pour empêcher le chargement et l'exécution d'un package non valide.</span><span class="sxs-lookup"><span data-stu-id="adfdb-104">You can use a digital signature, together with other settings, to prevent a package that is not valid from loading and running.</span></span>  
  
 <span data-ttu-id="adfdb-105">Avant de pouvoir signer un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="adfdb-105">Before you can sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, you must do the following tasks:</span></span>  
  
-   <span data-ttu-id="adfdb-106">Créez ou obtenez une clé privée à associer au certificat et stockez cette clé privée sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="adfdb-106">Create or obtain a private key to associate with the certificate, and store this private key on the local computer.</span></span>  
  
-   <span data-ttu-id="adfdb-107">Obtenez un certificat en vue de la signature du code à partir d'une autorité de certification approuvée.</span><span class="sxs-lookup"><span data-stu-id="adfdb-107">Obtain a certificate for the purpose of code signing from a trusted certification authority.</span></span> <span data-ttu-id="adfdb-108">Vous pouvez utiliser l'une des méthodes suivantes pour obtenir ou créer un certificat :</span><span class="sxs-lookup"><span data-stu-id="adfdb-108">You can use one of the following methods to obtain or create a certificate:</span></span>  
  
    -   <span data-ttu-id="adfdb-109">Obtenez un certificat à partir d'une autorité de certification commerciale publique qui émet des certificats.</span><span class="sxs-lookup"><span data-stu-id="adfdb-109">Obtain a certificate from a public, commercial certification authority that issues certificates.</span></span>  
  
    -   <span data-ttu-id="adfdb-110">Obtenez un certificat à partir d'un serveur de certificats, qui permet à une organisation d'émettre des certificats de façon interne.</span><span class="sxs-lookup"><span data-stu-id="adfdb-110">Obtain a certificate from a certificate server, that enables an organization to internally issue certificates.</span></span> <span data-ttu-id="adfdb-111">Vous devez ajouter le certificat racine utilisé pour signer le certificat dans le magasin **Autorités de certification racines de confiance** .</span><span class="sxs-lookup"><span data-stu-id="adfdb-111">You have to add the root certificate that is used to sign the certificate to the **Trusted Root Certification Authorities** store.</span></span> <span data-ttu-id="adfdb-112">Pour ajouter le certificat racine, vous pouvez utiliser le composant logiciel enfichable MMC ( [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console) Certificats.</span><span class="sxs-lookup"><span data-stu-id="adfdb-112">To add the root certificate, you can use the Certificates snap-in for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="adfdb-113">Pour plus d'informations, consultez la rubrique «[Services de certificats](https://go.microsoft.com/fwlink/?LinkId=100755)» dans MSDN Library (éventuellement en anglais).</span><span class="sxs-lookup"><span data-stu-id="adfdb-113">For more information, see the topic, "[Certificate Services](https://go.microsoft.com/fwlink/?LinkId=100755)," in the MSDN library.</span></span>  
  
    -   <span data-ttu-id="adfdb-114">Créez votre propre certificat à des fins de test uniquement.</span><span class="sxs-lookup"><span data-stu-id="adfdb-114">Create your own certificate for testing purposes only.</span></span> <span data-ttu-id="adfdb-115">L'outil de création de certificat Makecert.exe génère des certificats X.509 à des fins de tests.</span><span class="sxs-lookup"><span data-stu-id="adfdb-115">The Certificate Creation Tool (Makecert.exe) generates X.509 certificates for testing purposes.</span></span> <span data-ttu-id="adfdb-116">Pour plus d’informations, consultez la rubrique «[Outil Certificate Creation Tool (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)» dans MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="adfdb-116">For more information, see the topic, "[Certificate Creation Tool (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)," in the MSDN Library.</span></span>  
  
     <span data-ttu-id="adfdb-117">Pour plus d'informations sur les certificats, recherchez le composant logiciel enfichable Certificats dans l'aide en ligne.</span><span class="sxs-lookup"><span data-stu-id="adfdb-117">For more information about certificates, see the online Help for the Certificates snap-in.</span></span> <span data-ttu-id="adfdb-118">Pour plus d'informations sur la façon de signer des ressources numériques, consultez la rubrique «[Signature et vérification de code à l'aide d'Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)» dans MSDN Library (éventuellement en anglais).</span><span class="sxs-lookup"><span data-stu-id="adfdb-118">For more information about how to sign digital assets, see the topic, "[Signing and Checking Code with Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)," in the MSDN Library.</span></span>  
  
-   <span data-ttu-id="adfdb-119">Assurez-vous que le certificat a été activé pour la signature de code.</span><span class="sxs-lookup"><span data-stu-id="adfdb-119">Make sure that the certificate has been enabled for code signing.</span></span> <span data-ttu-id="adfdb-120">Pour déterminer si un certificat est activé pour la signature du code, examinez les propriétés du certificat dans le composant logiciel enfichable Certificats.</span><span class="sxs-lookup"><span data-stu-id="adfdb-120">To determine whether a certificate is enabled for code signing, review the properties of the certificate in the Certificates snap-in.</span></span>  
  
-   <span data-ttu-id="adfdb-121">Stockez le certificat dans le magasin Personnel.</span><span class="sxs-lookup"><span data-stu-id="adfdb-121">Store the certificate in the Personal store.</span></span>  
  
 <span data-ttu-id="adfdb-122">Après avoir terminé les tâches précédentes, vous pouvez utiliser la procédure suivante pour signer un package.</span><span class="sxs-lookup"><span data-stu-id="adfdb-122">After you have completed the previous tasks, you can use the following procedure to sign a package.</span></span>  
  
### <a name="to-sign-a-package"></a><span data-ttu-id="adfdb-123">Pour signer un package</span><span class="sxs-lookup"><span data-stu-id="adfdb-123">To sign a package</span></span>  
  
1.  <span data-ttu-id="adfdb-124">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package à signer.</span><span class="sxs-lookup"><span data-stu-id="adfdb-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to be signed.</span></span>  
  
2.  <span data-ttu-id="adfdb-125">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="adfdb-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="adfdb-126">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , dans le menu **SSIS** , cliquez sur **Signature numérique**.</span><span class="sxs-lookup"><span data-stu-id="adfdb-126">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, on the **SSIS** menu, click **Digital Signing**.</span></span>  
  
4.  <span data-ttu-id="adfdb-127">Dans la boîte de dialogue **Signature numérique** , cliquez sur **Signer**.</span><span class="sxs-lookup"><span data-stu-id="adfdb-127">In the **Digital Signing** dialog box, click **Sign**.</span></span>  
  
5.  <span data-ttu-id="adfdb-128">Dans la boîte de dialogue **Sélectionner un certificat** , sélectionnez un certificat.</span><span class="sxs-lookup"><span data-stu-id="adfdb-128">In the **Select a Certificate** dialog box, select a certificate.</span></span>  
  
6.  <span data-ttu-id="adfdb-129">(Facultatif) Cliquez sur **Afficher le certificat**pour afficher les informations sur le certificat.</span><span class="sxs-lookup"><span data-stu-id="adfdb-129">(Optional) Click **View Certificat**e to view certificate information.</span></span>  
  
7.  <span data-ttu-id="adfdb-130">Cliquez sur **OK** pour fermer la boîte de dialogue **Sélectionner un certificat** .</span><span class="sxs-lookup"><span data-stu-id="adfdb-130">Click **OK** to close the **Select a Certificate** dialog box.</span></span>  
  
8.  <span data-ttu-id="adfdb-131">Cliquez sur **OK** pour fermer la boîte de dialogue **Signature numérique** .</span><span class="sxs-lookup"><span data-stu-id="adfdb-131">Click **OK** to close the **Digital Signing** dialog box.</span></span>  
  
9. <span data-ttu-id="adfdb-132">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="adfdb-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
     <span data-ttu-id="adfdb-133">Bien que le package ait été signé, vous devez maintenant configurer [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pour vérifier la signature numérique avant de charger le package.</span><span class="sxs-lookup"><span data-stu-id="adfdb-133">Although the package has been signed, you must now configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] to check or verify the digital signature before loading the package.</span></span> <span data-ttu-id="adfdb-134">Pour plus d’informations, consultez [Identifier la source de packages à l’aide de signatures numériques](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="adfdb-134">For more information, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adfdb-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="adfdb-135">See Also</span></span>  
 [<span data-ttu-id="adfdb-136">Vue d’ensemble de la sécurité &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="adfdb-136">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
