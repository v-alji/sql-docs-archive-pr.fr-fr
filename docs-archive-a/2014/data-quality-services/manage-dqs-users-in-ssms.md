---
title: Gérer des utilisateurs DQS dans SSMS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 955af01d-00da-4c51-9311-f3848749df54
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bf8789abb59d168f39562f6486bb5c54bfc0fc50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613629"
---
# <a name="manage-dqs-users-in-ssms"></a><span data-ttu-id="d8f09-102">Gérer des utilisateurs DQS dans SSMS</span><span class="sxs-lookup"><span data-stu-id="d8f09-102">Manage DQS Users in SSMS</span></span>
  <span data-ttu-id="d8f09-103">Cette rubrique décrit comment créer des utilisateurs supplémentaires dans l'instance SQL Server à l'aide de SQL Server Management Studio et leur accorder des rôles [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) appropriés sur la base de données DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="d8f09-103">This topic describes how to create additional users in the SQL Server instance using SQL Server Management Studio, and grant them appropriate [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8f09-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d8f09-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8f09-105">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d8f09-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d8f09-106">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d8f09-106">Permissions</span></span>  
 <span data-ttu-id="d8f09-107">Votre compte d'utilisateur Windows doit être un membre du rôle serveur fixe approprié (tel que securityadmin, serveradmin ou sysadmin) pour créer une connexion SQL et lui accorder des rôles DQS appropriés.</span><span class="sxs-lookup"><span data-stu-id="d8f09-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant appropriate DQS roles.</span></span>  
  
##  <a name="create-a-sql-login-and-grant-dqs-role"></a><a name="GrantRoles"></a><span data-ttu-id="d8f09-108">Créer une connexion SQL et accorder un rôle DQS</span><span class="sxs-lookup"><span data-stu-id="d8f09-108">Create a SQL Login and Grant DQS Role</span></span>  
  
1.  <span data-ttu-id="d8f09-109">Démarrez Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="d8f09-109">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="d8f09-110">Dans Microsoft SQL Server Management Studio, développez votre instance SQL Server, puis développez **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="d8f09-110">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="d8f09-111">Cliquez avec le bouton droit sur le dossier **Sécurité** , pointez sur **Nouveau**, puis cliquez sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="d8f09-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="d8f09-112">Dans la boîte de dialogue **Nouvelle connexion**, spécifiez le nom d’un utilisateur Windows dans la zone **Nom de connexion**, spécifiez le type d’authentification **Authentification Windows**, puis cliquez sur **Rechercher** pour valider l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d8f09-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8f09-113">DQS prend en charge uniquement l'authentification Windows ; l'authentification SQL Server n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d8f09-113">DQS only supports Windows authentication; SQL Server authentication is not supported.</span></span>  
  
5.  <span data-ttu-id="d8f09-114">Une fois l'utilisateur validé, dans le volet de gauche, cliquez sur **Mappage de l'utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="d8f09-114">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="d8f09-115">Dans le volet droit, cochez la case sous la colonne **Mappage** pour la base de données **DQS_MAIN** , puis cochez la case **dqs_administrator**, **dqs_kb_editor**ou **dqs_kb_operator** dans le volet **Appartenance au rôle de base de données : DQS_MAIN** , selon le niveau d’accès nécessaire pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d8f09-115">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span>  
  
7.  <span data-ttu-id="d8f09-116">Dans la boîte de dialogue **Nouvelle connexion**, cliquez sur **OK** pour appliquer les modifications.</span><span class="sxs-lookup"><span data-stu-id="d8f09-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8f09-117">Si vous accordez le rôle **dqs_administrator** à un utilisateur, appliquez les modifications, puis revérifiez les autorisations de l’utilisateur ; les deux autres cases de rôles DQS (**dq_kb_editor** et **dqs_kb_operator**) sont aussi cochées.</span><span class="sxs-lookup"><span data-stu-id="d8f09-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
  
