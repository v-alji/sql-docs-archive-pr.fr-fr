---
title: Affecter des rôles DQS aux utilisateurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: afb445b5-bdbe-4bfe-844f-344766cdc2b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 62ff5eb03fa46279ee1b8a1329c58bd69361ef82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705436"
---
# <a name="grant-dqs-roles-to-users"></a><span data-ttu-id="20627-102">Affecter des rôles DQS aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="20627-102">Grant DQS Roles to Users</span></span>
  <span data-ttu-id="20627-103">Cette rubrique décrit comment créer des connexions SQL selon un principal Windows, et accorde ces rôles de [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) sur la base de données DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="20627-103">This topic describes how to create SQL logins based on a Windows principal, and grant [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="20627-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="20627-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="20627-105">Vous devez avoir terminé l'installation du [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] en exécutant le fichier DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="20627-105">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="20627-106">Pour plus d’informations, consultez [Exécuter DQSInstaller.exe pour terminer l’installation du serveur DQS](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="20627-106">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="20627-107">Votre compte d'utilisateur Windows doit être un membre du rôle serveur fixe sysadmin approprié (tel que securityadmin, serveradmin ou sysadmin) pour créer une connexion SQL et lui accorder des rôles DQS.</span><span class="sxs-lookup"><span data-stu-id="20627-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant them DQS roles.</span></span>  
  
### <a name="to-create-sql-login-and-grant-dqs-roles"></a><span data-ttu-id="20627-108">Pour créer une connexion SQL et accorder des rôles DQS</span><span class="sxs-lookup"><span data-stu-id="20627-108">To create SQL login and grant DQS roles</span></span>  
  
1.  <span data-ttu-id="20627-109">Démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20627-109">Start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="20627-110">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez votre instance de SQL Server, puis développez **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="20627-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="20627-111">Cliquez avec le bouton droit sur le dossier **Sécurité** , pointez sur **Nouveau**, puis cliquez sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="20627-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="20627-112">Dans la boîte de dialogue **Nouvelle connexion**, spécifiez le nom d’un utilisateur Windows dans la zone **Nom de connexion**, spécifiez le type d’authentification **Authentification Windows**, puis cliquez sur **Rechercher** pour valider l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="20627-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
5.  <span data-ttu-id="20627-113">Une fois l'utilisateur validé, dans le volet de gauche, cliquez sur **Mappage de l'utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="20627-113">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="20627-114">Dans le volet droit, cochez la case sous la colonne **Mappage** pour la base de données **DQS_MAIN** , puis cochez la case **dqs_administrator**, **dqs_kb_editor**ou **dqs_kb_operator** dans le volet **Appartenance au rôle de base de données : DQS_MAIN** , selon le niveau d’accès nécessaire pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="20627-114">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span> <span data-ttu-id="20627-115">Pour plus d'informations sur les trois rôles DQS, consultez [Sécurité DQS](../dqs-security.md).</span><span class="sxs-lookup"><span data-stu-id="20627-115">For information about the three DQS roles, see [DQS Security](../dqs-security.md).</span></span>  
  
7.  <span data-ttu-id="20627-116">Dans la boîte de dialogue **Nouvelle connexion**, cliquez sur **OK** pour appliquer les modifications.</span><span class="sxs-lookup"><span data-stu-id="20627-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="20627-117">Si vous accordez le rôle **dqs_administrator** à un utilisateur, appliquez les modifications, puis revérifiez les autorisations de l’utilisateur ; les deux autres cases de rôles DQS (**dq_kb_editor** et **dqs_kb_operator**) sont aussi cochées.</span><span class="sxs-lookup"><span data-stu-id="20627-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="20627-118">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="20627-118">Next Steps</span></span>  
 <span data-ttu-id="20627-119">Essayez d'ouvrir une session sur le [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] à l'aide du compte d'utilisateur Windows pour lequel vous venez de créer une connexion SQL et d'accorder un rôle DQS.</span><span class="sxs-lookup"><span data-stu-id="20627-119">Try logging on to [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] by using the Windows user account for which you just created a SQL login, and granted a DQS role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20627-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20627-120">See Also</span></span>  
 <span data-ttu-id="20627-121">[Installer Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="20627-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="20627-122">Créer un compte de connexion</span><span class="sxs-lookup"><span data-stu-id="20627-122">Create a Login</span></span>](../../relational-databases/security/authentication-access/create-a-login.md)  
  
  
