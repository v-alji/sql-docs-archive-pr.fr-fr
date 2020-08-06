---
title: Tester les autorisations d’un utilisateur (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 83a03b85-ea7f-4b4a-b19b-f7eca534ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8c109eebb4bf06bf7605ca3b7b5930ce18951e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610702"
---
# <a name="test-a-user39s-permissions-master-data-services"></a><span data-ttu-id="d0ce3-102">Tester les autorisations d’un utilisateur (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d0ce3-102">Test a User&#39;s Permissions (Master Data Services)</span></span>
  <span data-ttu-id="d0ce3-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous pouvez créer un utilisateur de test et vous connecter à l'application Web pour tester les autorisations. Lorsqu'un utilisateur tente d'accéder à l'URL [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , les informations d'identification de l'utilisateur sont authentifiées.</span><span class="sxs-lookup"><span data-stu-id="d0ce3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can create a test user and log into the web application to test permissions.When a user attempts to access the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] URL, the user's credentials are authenticated.</span></span> <span data-ttu-id="d0ce3-104">Dans Internet Explorer, les paramètres de sécurité déterminent si cette opération se produit automatiquement ou si l'utilisateur doit entrer un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d0ce3-104">In Internet Explorer, security settings control whether this occurs automatically or if the user must enter a user name and password.</span></span> <span data-ttu-id="d0ce3-105">Pour modifier ces paramètres, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d0ce3-105">To change these settings, complete the following steps:</span></span>  
  
### <a name="to-test-a-users-security"></a><span data-ttu-id="d0ce3-106">Pour tester la sécurité d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="d0ce3-106">To test a user's security</span></span>  
  
1.  <span data-ttu-id="d0ce3-107">Dans Internet Explorer 7 et version ultérieure, cliquez sur **Outils**, sur **Options Internet**, puis sur l'onglet **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="d0ce3-107">In Internet Explorer 7 and later, click **Tools**, **Internet Options**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="d0ce3-108">Cliquez sur **Intranet local** , puis sur le bouton **Personnaliser le niveau** .</span><span class="sxs-lookup"><span data-stu-id="d0ce3-108">Click **Local Intranet** and then the **Custom Level** button.</span></span>  
  
3.  <span data-ttu-id="d0ce3-109">Dans la section **Authentification utilisateur** , choisissez **Demander le nom d'utilisateur et le mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="d0ce3-109">In the **User Authentication** section, choose **Prompt for user name and password**.</span></span>  
  
4.  <span data-ttu-id="d0ce3-110">La prochaine fois que vous ouvrez la fenêtre de navigateur, vous serez invité à fournir un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d0ce3-110">The next time you open the browser window, you will be prompted for a user name and password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ce3-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d0ce3-111">See Also</span></span>  
 [<span data-ttu-id="d0ce3-112">Sécurité &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d0ce3-112">Security &#40;Master Data Services&#41;</span></span>](security-master-data-services.md)  
  
  
