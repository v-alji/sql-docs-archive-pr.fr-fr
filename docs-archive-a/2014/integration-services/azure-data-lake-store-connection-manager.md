---
title: Gestionnaire de connexions Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSCM.F1
- SQL11.DTS.DESIGNER.AFPADLSCM.F1
ms.assetid: 7f1323f9-9dc3-4378-9c70-bbc65bfeabfd
author: yualan
ms.author: chugu
ms.openlocfilehash: 1ab6e90aad6472cc10bbb12cf4ca17def501bf00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707735"
---
# <a name="azure-data-lake-store-connection-manager"></a><span data-ttu-id="f8993-102">Gestionnaire de connexions Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="f8993-102">Azure Data Lake Store Connection Manager</span></span>
  <span data-ttu-id="f8993-103">Le **gestionnaire de connexions Azure Data Lake Store** permet à un package SSIS de se connecter à un service Azure Data Lake Store par le biais de deux types d’authentification : Identité de l’utilisateur Azure AD et Identité du service Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f8993-103">The **Azure Data Lake Store connection manager** enables an SSIS package to connect to an Azure Data Lake Store service through two authentication types: Azure AD User Identity and Azure AD Service Identity.</span></span>  

## <a name="configure-the-azure-data-lake-store-connection-manager"></a><span data-ttu-id="f8993-104">Configurer le gestionnaire de connexions Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="f8993-104">Configure the Azure Data Lake Store Connection Manager</span></span> 
  
1.  <span data-ttu-id="f8993-105">Dans la boîte de dialogue **Ajout d’un gestionnaire de connexions SSIS** , sélectionnez **AzureDataLake**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f8993-105">In the **Add SSIS Connection Manager** dialog box, select **AzureDataLake**, and click **Add**.</span></span>   
  
2.  <span data-ttu-id="f8993-106">Dans la boîte de dialogue Éditeur du gestionnaire de connexions Azure Data Lake Store, tapez l’URL de l’hôte Azure Data Lake Store dans le champ **Hôte ADLS** .</span><span class="sxs-lookup"><span data-stu-id="f8993-106">In the Azure Data Lake Store Connection Manager Editor dialog box, type in the Azure Data Lake Store host URL in **ADLS Host** field.</span></span> <span data-ttu-id="f8993-107">Par exemple : https : \/ /test.azuredatalakestore.net ou test.azuredatalakestore.net.</span><span class="sxs-lookup"><span data-stu-id="f8993-107">For example: https:\//test.azuredatalakestore.net or test.azuredatalakestore.net.</span></span>
  
3.  <span data-ttu-id="f8993-108">Choisissez le type d’authentification correspondant pour accéder aux données Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="f8993-108">Choose corresponding authentication type to access Azure Data Lake Store data.</span></span>

    1.  <span data-ttu-id="f8993-109">Si vous avez sélectionné l’option d’authentification **Identité de l’utilisateur Azure AD** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8993-109">If you selected **Azure AD User Identity** authentication option, do the following:</span></span>

        1. <span data-ttu-id="f8993-110">Spécifiez des valeurs pour les champs **Nom d’utilisateur** et **Mot de passe** .</span><span class="sxs-lookup"><span data-stu-id="f8993-110">Specify values for the **User Name** and **Password** field.</span></span> 
    
        2. <span data-ttu-id="f8993-111">Cliquez sur le bouton **Tester la connexion** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="f8993-111">Click **Test Connection** button to test the connection.</span></span> <span data-ttu-id="f8993-112">Si vous et votre administrateur locataire n’avez pas déjà autorisé SSIS à accéder à vos données Azure Data Lake Store, vous devez cliquer sur le bouton **Accepter** pour autoriser SSIS à accéder à vos données Azure Data Lake Store dans la boîte de dialogue indépendante.</span><span class="sxs-lookup"><span data-stu-id="f8993-112">If you and your tenant administrator didn't consent SSIS to access your Azure Data Lake Store data before, you need click **Accept** button to consent SSIS to access your Azure Data Lake Store data in the pop out dialog.</span></span> <span data-ttu-id="f8993-113">Pour plus d’informations sur cette procédure de consentement, consultez [Intégration d’applications dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="f8993-113">For more information about this consent experience, see [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span></span>
    
        > [!NOTE] 
        > <span data-ttu-id="f8993-114">Pour l’option d’authentification Identité de l’utilisateur Azure AD, l’authentification multifacteur avec un compte Microsoft n’est PAS prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f8993-114">For Azure AD User Identity authentication option, multi-factor authentication and Microsoft account is NOT supported.</span></span>
    
    2.  <span data-ttu-id="f8993-115">Si vous avez sélectionné l’option d’authentification **Identité du service Azure AD** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8993-115">If you selected **Azure AD Service Identity** authentication option, do the following:</span></span>
        1. <span data-ttu-id="f8993-116">Créez une application AAD et un principal du service qui peuvent accéder aux ressources Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="f8993-116">Create an AAD application and service principal that can access Azure Data Lake resources.</span></span>
    
        2. <span data-ttu-id="f8993-117">Affectez à cette application AAD les autorisations correspondantes pour accéder à vos ressources Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="f8993-117">Assign this AAD application corresponding permissions to access your Azure Data Lake resources.</span></span> <span data-ttu-id="f8993-118">Pour plus d’informations sur cette option d’authentification, consultez [Utiliser le portail pour créer une application Active Directory et un principal du service qui peuvent accéder aux ressources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="f8993-118">For more information about this authentication option, see [Use portal to create Active Directory application and service principal that can access resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>
    
        3. <span data-ttu-id="f8993-119">Spécifiez des valeurs pour les champs **ID client**, **Clé secrète** et **Nom du locataire** .</span><span class="sxs-lookup"><span data-stu-id="f8993-119">Specify values for **Client Id**, **Secret Key** and **Tenant Name** field.</span></span>
    
        4. <span data-ttu-id="f8993-120">Cliquez sur le bouton **Tester la connexion** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="f8993-120">Click **Test Connection** button to test the connection.</span></span>  
  
4.  <span data-ttu-id="f8993-121">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f8993-121">Click **OK** to close the dialog box.</span></span>  
  
    <span data-ttu-id="f8993-122">Les propriétés du gestionnaire de connexions que vous avez créées apparaissent dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="f8993-122">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
