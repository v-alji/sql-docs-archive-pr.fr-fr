---
title: Configurer les autorisations du système de fichiers pour l’accès au moteur de base de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- file system permissions
- service account [SQL Server], file system permissions
- permissions [SQL Server], file system
ms.assetid: 78bba43c-4edb-4216-84ac-d6246ae5546d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1d9abbd095f2d5be7415ed28a17fb710ff8ab504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614848"
---
# <a name="configure-file-system-permissions-for-database-engine-access"></a><span data-ttu-id="1ff88-102">Configurer les autorisations du système de fichiers pour l'accès au moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="1ff88-102">Configure File System Permissions for Database Engine Access</span></span>
  <span data-ttu-id="1ff88-103">Cette rubrique explique comment octroyer au [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]un accès de système de fichiers à l'emplacement où sont stockés les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="1ff88-103">This topic describes how to grant the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], file system access to the location where database files are stored.</span></span> <span data-ttu-id="1ff88-104">Le service [!INCLUDE[ssDE](../../includes/ssde-md.md)] doit disposer d'une autorisation du système de fichiers Windows pour accéder au dossier de fichiers dans lequel sont stockés les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="1ff88-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] service must have permission of the Windows file system to access the file folder where database files are stored.</span></span> <span data-ttu-id="1ff88-105">L'autorisation sur l'emplacement par défaut est configurée lors de l'installation.</span><span class="sxs-lookup"><span data-stu-id="1ff88-105">Permission to the default location is configured during setup.</span></span> <span data-ttu-id="1ff88-106">Si vous placez vos fichiers de base de données à un emplacement différent, vous devrez peut-être procéder comme suit pour octroyer au [!INCLUDE[ssDE](../../includes/ssde-md.md)] une autorisation de contrôle total sur cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="1ff88-106">If you place your database files in a different location, you might need to follow these steps to grant the [!INCLUDE[ssDE](../../includes/ssde-md.md)] the full control permission to that location.</span></span>  
  
 <span data-ttu-id="1ff88-107">Depuis [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , les autorisations sont affectées au SID par service pour chacun de ses services.</span><span class="sxs-lookup"><span data-stu-id="1ff88-107">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permissions are assigned to the per-service SID for each of its services.</span></span> <span data-ttu-id="1ff88-108">Ce système aide à fournir une isolation de service et une défense en profondeur.</span><span class="sxs-lookup"><span data-stu-id="1ff88-108">This system helps provide service isolation and defense in depth.</span></span> <span data-ttu-id="1ff88-109">Le SID par service est dérivé du nom du service et est propre à chaque service.</span><span class="sxs-lookup"><span data-stu-id="1ff88-109">The per-service SID is derived from the service name and is unique to each service.</span></span> <span data-ttu-id="1ff88-110">La rubrique [Configurer les comptes de service Windows et les autorisations](configure-windows-service-accounts-and-permissions.md) décrit le SID par service et fournit les noms dans la section **Privilèges et droits Windows**.</span><span class="sxs-lookup"><span data-stu-id="1ff88-110">The topic [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md) describes the per-service SID and provides the names in the section **Windows Privileges and Rights**.</span></span> <span data-ttu-id="1ff88-111">C'est le SID par service qui doit bénéficier d'une autorisation d'accès à l'emplacement de fichier.</span><span class="sxs-lookup"><span data-stu-id="1ff88-111">It is the per-service SID that must be assigned the access permission on the file location.</span></span>  
  
## <a name="to-grant-file-system-permission-to-the-per-service-sid"></a><span data-ttu-id="1ff88-112">Pour octroyer une autorisation de système de fichiers au SID par service</span><span class="sxs-lookup"><span data-stu-id="1ff88-112">To Grant File System Permission to the Per-service SID</span></span>  
  
1.  <span data-ttu-id="1ff88-113">À l'aide de l'Explorateur Windows, accédez à l'emplacement du système de fichiers où sont stockés les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="1ff88-113">Using Windows Explorer, navigate to the file system location where the database files are stored.</span></span> <span data-ttu-id="1ff88-114">Cliquez avec le bouton droit sur le dossier du système de fichiers, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1ff88-114">Right-click the file system folder, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="1ff88-115">Sous l’onglet **Sécurité** , cliquez sur **Modifier**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1ff88-115">On the **Security** tab, click **Edit**, and then **Add**.</span></span>  
  
3.  <span data-ttu-id="1ff88-116">Dans la boîte de dialogue **Choisir des utilisateurs, un ordinateur, un compte de service ou des groupes** , cliquez sur **Emplacements**, en haut de la liste des emplacements, sélectionnez le nom de votre ordinateur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ff88-116">In the **Select Users, Computer, Service Account, or Groups** dialog box, click **Locations**, at the top of the location list, select your computer name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="1ff88-117">Dans la zone **Entrez les noms des objets à sélectionner** , tapez le nom du SID par service figurant dans la rubrique de la documentation en ligne **configurer les comptes de service Windows et les autorisations**.</span><span class="sxs-lookup"><span data-stu-id="1ff88-117">In the **Enter the object names to select** box, type the name of the per-service SID listed in the Books Online topic **Configure Windows Service Accounts and Permissions**.</span></span> <span data-ttu-id="1ff88-118">(Pour le [!INCLUDE[ssDE](../../includes/ssde-md.md)] SID par service, utilisez **NT SERVICE\MSSQLSERVER** pour une instance par défaut ou **NT SERVICE\MSSQL $ InstanceName** pour une instance nommée.)</span><span class="sxs-lookup"><span data-stu-id="1ff88-118">(For the [!INCLUDE[ssDE](../../includes/ssde-md.md)] per service SID, use **NT SERVICE\MSSQLSERVER** for a default instance, or **NT SERVICE\MSSQL$InstanceName** for a named instance.)</span></span>  
  
5.  <span data-ttu-id="1ff88-119">Cliquez sur **Vérifier les noms** pour valider l’entrée.</span><span class="sxs-lookup"><span data-stu-id="1ff88-119">Click **Check Names** to validate the entry.</span></span> <span data-ttu-id="1ff88-120">La validation échoue souvent et peut indiquer que le nom était introuvable.</span><span class="sxs-lookup"><span data-stu-id="1ff88-120">The validation often fails, and might advise you that the name was not found.</span></span> <span data-ttu-id="1ff88-121">Quand vous cliquez sur **OK**, une boîte de dialogue **Noms multiples trouvés** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1ff88-121">When you click **OK**, a **Multiple Names Found** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="1ff88-122">Sélectionnez maintenant le SID par service, **MSSQLSERVER** ou **NT SERVICE\MSSQL $ nom_instance**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ff88-122">Now select the per-service SID, either **MSSQLSERVER** or **NT SERVICE\MSSQL$InstanceName**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="1ff88-123">Cliquez à nouveau sur **OK** pour revenir à la boîte de dialogue **autorisations** .</span><span class="sxs-lookup"><span data-stu-id="1ff88-123">Click **OK** again to return to the **Permissions** dialog box.</span></span>  
  
8.  <span data-ttu-id="1ff88-124">Dans la zone noms de **groupes ou d’utilisateurs** , sélectionnez le SID par service, puis dans la zone **autorisations pour** \<name> , activez la case à cocher **autoriser** pour **contrôle total**.</span><span class="sxs-lookup"><span data-stu-id="1ff88-124">In the **Group or user** names box, select the per-service SID, and then in the **Permissions for** \<name> box, select the **Allow** check box for **Full control**.</span></span>  
  
9. <span data-ttu-id="1ff88-125">Cliquez sur **Appliquer**, puis cliquez à deux reprises sur **OK** pour quitter la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="1ff88-125">Click **Apply**, and then click **OK** twice to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff88-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ff88-126">See Also</span></span>  
 <span data-ttu-id="1ff88-127">[Gérer les services du moteur de base de données](manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="1ff88-127">[Manage the Database Engine Services](manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="1ff88-128">[Déplacer des bases de données système](../../relational-databases/databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="1ff88-128">[Move System Databases](../../relational-databases/databases/system-databases.md) </span></span>  
 [<span data-ttu-id="1ff88-129">Déplacer des bases de données utilisateur</span><span class="sxs-lookup"><span data-stu-id="1ff88-129">Move User Databases</span></span>](../../relational-databases/databases/move-user-databases.md)  
  
  
