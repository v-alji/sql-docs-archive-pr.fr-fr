---
title: MSSQLSERVER_17832 | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17828 (Database Engine error)
- maxtokensize
- 17832 (Database Engine error)
- login packet (bad)
ms.assetid: bd56ffe4-0855-4ada-8aca-251fbc6ff2ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dba214e2cce04ff2583e12ae7cee9b54373390a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696903"
---
# <a name="mssqlserver_17832"></a><span data-ttu-id="54b88-102">MSSQLSERVER_17832</span><span class="sxs-lookup"><span data-stu-id="54b88-102">MSSQLSERVER_17832</span></span>
    
## <a name="details"></a><span data-ttu-id="54b88-103">Détails</span><span class="sxs-lookup"><span data-stu-id="54b88-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54b88-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="54b88-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="54b88-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="54b88-105">Event ID</span></span>|<span data-ttu-id="54b88-106">17832</span><span class="sxs-lookup"><span data-stu-id="54b88-106">17832</span></span>|  
|<span data-ttu-id="54b88-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="54b88-107">Event Source</span></span>|<span data-ttu-id="54b88-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="54b88-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="54b88-109">Composant</span><span class="sxs-lookup"><span data-stu-id="54b88-109">Component</span></span>|<span data-ttu-id="54b88-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="54b88-110">SQLEngine</span></span>|  
|<span data-ttu-id="54b88-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="54b88-111">Symbolic Name</span></span>|<span data-ttu-id="54b88-112">SRV_BAD_LOGIN_PKT</span><span class="sxs-lookup"><span data-stu-id="54b88-112">SRV_BAD_LOGIN_PKT</span></span>|  
|<span data-ttu-id="54b88-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="54b88-113">Message Text</span></span>|<span data-ttu-id="54b88-114">Le paquet d'ouverture de session servant à ouvrir la connexion présente une structure non valide ; la connexion a été fermée.</span><span class="sxs-lookup"><span data-stu-id="54b88-114">The login packet used to open the connection is structurally invalid; the connection has been closed.</span></span> <span data-ttu-id="54b88-115">Contactez le fournisseur de la bibliothèque cliente.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="54b88-115">Please contact the vendor of the client library.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="54b88-116">Explication</span><span class="sxs-lookup"><span data-stu-id="54b88-116">Explanation</span></span>  
 <span data-ttu-id="54b88-117">L'ordinateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'a pas pu traiter le paquet d'ouverture de session du client,</span><span class="sxs-lookup"><span data-stu-id="54b88-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer was unable to process the client login packet.</span></span> <span data-ttu-id="54b88-118">soit parce que le paquet n'a pas été créé correctement, soit parce qu'il a été endommagé pendant la transmission.</span><span class="sxs-lookup"><span data-stu-id="54b88-118">This may be because the packet was created improperly or because the packet was damaged during transmission.</span></span> <span data-ttu-id="54b88-119">Ce problème peut également être dû à la configuration de l'ordinateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54b88-119">It can also be caused by the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="54b88-120">L'adresse IP répertoriée correspond à l'adresse du client.</span><span class="sxs-lookup"><span data-stu-id="54b88-120">The IP address listed is the address of the client computer.</span></span>  
  
### <a name="more-information"></a><span data-ttu-id="54b88-121">Informations complémentaires</span><span class="sxs-lookup"><span data-stu-id="54b88-121">More Information</span></span>  
 <span data-ttu-id="54b88-122">Lorsque vous utilisez l'authentification Windows dans un environnement Kerberos, un client reçoit un ticket Kerberos qui contient un certificat PAC (Privilege Attribute Certificate).</span><span class="sxs-lookup"><span data-stu-id="54b88-122">When using Windows Authentication in a Kerberos environment, a client receives a Kerberos ticket that contains a Privilege Attribute Certificate (PAC).</span></span> <span data-ttu-id="54b88-123">Le certificat PAC contient différents types de données d'autorisation, notamment les groupes dont l'utilisateur est membre, les droits dont il dispose et les stratégies qui s'appliquent à lui.</span><span class="sxs-lookup"><span data-stu-id="54b88-123">The PAC contains various types of authorization data including groups that the user is a member of, rights the user has, and what policies apply to the user.</span></span> <span data-ttu-id="54b88-124">Lorsque le client reçoit le ticket Kerberos, les informations contenues dans le certificat PAC sont utilisées pour générer le jeton d'accès de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="54b88-124">When the client receives the Kerberos ticket, the information contained in the PAC is used to generate the user's access token.</span></span> <span data-ttu-id="54b88-125">Le client présente le jeton à l'ordinateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans le cadre du paquet d'ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="54b88-125">The client presents the token to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer as part of the login packet.</span></span>  
  
 <span data-ttu-id="54b88-126">Si le jeton a été créé incorrectement ou endommagé pendant la transmission, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas proposer d'informations supplémentaires sur le problème.</span><span class="sxs-lookup"><span data-stu-id="54b88-126">If the token was improperly created or damaged during transmission, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot offer additional information about the problem.</span></span>  
  
 <span data-ttu-id="54b88-127">Lorsque l'utilisateur est membre de nombreux groupes ou possède de nombreuses stratégies, le jeton peut devenir trop volumineux et ne pas les répertorier tous et toutes.</span><span class="sxs-lookup"><span data-stu-id="54b88-127">When the user is a member of many groups or has many policies, the token may grow larger than normal to list them all.</span></span> <span data-ttu-id="54b88-128">Si le jeton dépasse la valeur **MaxTokenSize** du serveur, le client ne parvient pas à se connecter, ce qui génère une erreur réseau générale et l’erreur 17832 peut se produire.</span><span class="sxs-lookup"><span data-stu-id="54b88-128">If the token grows larger than the **MaxTokenSize** value of the server computer, the client fails to connect with a General Network Error (GNE) and error 17832 can occur.</span></span> <span data-ttu-id="54b88-129">Ce problème peut affecter uniquement certains utilisateurs : ceux qui appartiennent à de nombreux groupes ou stratégies.</span><span class="sxs-lookup"><span data-stu-id="54b88-129">This problem may affect only some users: users with many groups or policies.</span></span> <span data-ttu-id="54b88-130">Quand le problème est lié à la valeur **MaxTokenSize** du serveur, l’erreur 17832 mentionnée dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est accompagnée d’une erreur dont l’état est 9.</span><span class="sxs-lookup"><span data-stu-id="54b88-130">When the problem is the **MaxTokenSize** value of the server computer, error 17832 in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log will be accompanied by an error with state 9.</span></span> <span data-ttu-id="54b88-131">Pour plus d’informations sur Kerberos et la valeur **MaxTokenSize**, consultez [KB327825](https://support.microsoft.com/kb/327825).</span><span class="sxs-lookup"><span data-stu-id="54b88-131">For additional details about the Kerberos and **MaxTokenSize**, see [KB327825](https://support.microsoft.com/kb/327825).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54b88-132">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="54b88-132">User Action</span></span>  
 <span data-ttu-id="54b88-133">Pour résoudre ce problème, augmentez la valeur **MaxTokenSize** du serveur à une taille assez importante pour contenir le jeton le plus volumineux de tous les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="54b88-133">To resolve this problem, increase the **MaxTokenSize** value of the server computer, to a size large enough to contain the largest token of any user in your organization.</span></span> <span data-ttu-id="54b88-134">Pour rechercher la taille de jeton correcte pour votre organisation, envisagez d’utiliser l’application **Tokensz**.</span><span class="sxs-lookup"><span data-stu-id="54b88-134">To research the correct token size for your organization, consider using the **Tokensz** application.</span></span>   
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="54b88-135">**Pour modifier le MaxTokenSize sur l’ordinateur serveur**</span><span class="sxs-lookup"><span data-stu-id="54b88-135">**To change the MaxTokenSize  on the server computer**</span></span>  
  
1.  <span data-ttu-id="54b88-136">Dans le menu **Démarrer** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="54b88-136">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="54b88-137">Tapez `regedit` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b88-137">Type `regedit`, and then click **OK**.</span></span> <span data-ttu-id="54b88-138">(Si la boîte de dialogue **Contrôle de compte d’utilisateur** s’affiche, cliquez sur **Continuer**.)</span><span class="sxs-lookup"><span data-stu-id="54b88-138">(If the **User Account Control** dialog box appears, click **Continue**.)</span></span>  
  
3.  <span data-ttu-id="54b88-139">Accédez à **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span><span class="sxs-lookup"><span data-stu-id="54b88-139">Navigate to **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span></span>  
  
4.  <span data-ttu-id="54b88-140">Si le paramètre **MaxTokenSize** est absent, cliquez avec le bouton droit sur **Paramètres**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)** .</span><span class="sxs-lookup"><span data-stu-id="54b88-140">If the **MaxTokenSize** parameter is not present, right-click **Parameters**, point to **New**, and then click **DWORD (32-bit)** Value.</span></span> <span data-ttu-id="54b88-141">Nommez l’entrée de Registre **MaxTokenSize**.</span><span class="sxs-lookup"><span data-stu-id="54b88-141">Name the registry entry **MaxTokenSize**.</span></span>  
  
5.  <span data-ttu-id="54b88-142">Cliquez avec le bouton droit sur **MaxTokenSize**, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="54b88-142">Right-click **MaxTokenSize**, and then click **Modify**.</span></span>  
  
6.  <span data-ttu-id="54b88-143">Dans la zone **Données de la valeur**, tapez la valeur **MaxTokenSize** souhaitée.</span><span class="sxs-lookup"><span data-stu-id="54b88-143">In the **Value data** box type the desired **MaxTokenSize** value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="54b88-144">La valeur hexadécimale ffff (valeur décimale 65535) est la taille de jeton maximale recommandée.</span><span class="sxs-lookup"><span data-stu-id="54b88-144">Hexadecimal value ffff (decimal value 65535) is the maximum recommended token size.</span></span> <span data-ttu-id="54b88-145">La définition de cette valeur permettra probablement de résoudre le problème, mais elle peut nuire aux performances de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="54b88-145">Providing this value would probably solve the problem, but could have negative computer-wide effects with regard to performance.</span></span> <span data-ttu-id="54b88-146">Nous vous recommandons de déterminer la plus petite valeur **MaxTokenSize** possible représentant le jeton le plus volumineux des utilisateurs de votre organisation et d’entrer cette valeur.</span><span class="sxs-lookup"><span data-stu-id="54b88-146">We recommend that you establish the minimum **MaxTokenSize** value that allows for the largest token of any user in your organization and enter that value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="54b88-147">Fermez l’**Éditeur de Registre**.</span><span class="sxs-lookup"><span data-stu-id="54b88-147">Close **Registry Editor**.</span></span>  
  
9. <span data-ttu-id="54b88-148">Redémarrez l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="54b88-148">Restart the computer.</span></span>  
  
  
