---
title: Afficher ou modifier des filtres et des analyseurs lexicaux inscrits | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text search [SQL Server], word breakers
- full-text search [SQL Server], filters
- filters [full-text search]
- word breakers [full-text search]
ms.assetid: f88c54df-b1aa-4701-807f-dc92c32363fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79ad7f1f7df15fed21a132bbe253adc7185d8c06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697811"
---
# <a name="view-or-change-registered-filters-and-word-breakers"></a><span data-ttu-id="b171b-102">Afficher ou modifier des filtres et des analyseurs lexicaux inscrits</span><span class="sxs-lookup"><span data-stu-id="b171b-102">View or Change Registered Filters and Word Breakers</span></span>
  <span data-ttu-id="b171b-103">Après l'installation ou la désinstallation des analyseurs lexicaux ou des filtres sur un système, les modifications n'entrent pas automatiquement en vigueur sur les instances de serveur.</span><span class="sxs-lookup"><span data-stu-id="b171b-103">After any word breakers or filters are installed or uninstalled on a system, the changes do not automatically take effect on server instances.</span></span> <span data-ttu-id="b171b-104">Cette rubrique explique comment afficher les analyseurs lexicaux ou les filtres actuellement inscrits et comment inscrire les analyseurs lexicaux et les filtres récemment installés sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b171b-104">This topic describes how to view the currently registered word breaker or filters and how to register newly installed word breakers and filters on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-a-list-of-languages-whose-word-breakers-are-currently-registered"></a><span data-ttu-id="b171b-105">Pour afficher la liste des langues dont les analyseurs lexicaux sont actuellement inscrits</span><span class="sxs-lookup"><span data-stu-id="b171b-105">To view a list of languages whose word breakers are currently registered</span></span>  
  
1.  <span data-ttu-id="b171b-106">Utilisez la vue de catalogue [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="b171b-106">Use the [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) catalog view, as follows:</span></span>  
  
    ```  
    SELECT * FROM sys.fulltext_languages;   
    ```  
  
### <a name="to-view-a-list-of-the-filters-that-are-currently-registered"></a><span data-ttu-id="b171b-107">Pour afficher la liste des filtres actuellement inscrits</span><span class="sxs-lookup"><span data-stu-id="b171b-107">To view a list of the filters that are currently registered</span></span>  
  
1.  <span data-ttu-id="b171b-108">Utilisez la procédure stockée système [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="b171b-108">Use the [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) system stored procedure, as follows:</span></span>  
  
    ```  
    EXEC sp_help_fulltext_system_components 'filter';    
    ```  
  
### <a name="to-register-newly-installed-word-breakers-and-filters"></a><span data-ttu-id="b171b-109">Pour inscrire les analyseurs lexicaux et les filtres récemment installés</span><span class="sxs-lookup"><span data-stu-id="b171b-109">To register newly installed word breakers and filters</span></span>  
  
1.  <span data-ttu-id="b171b-110">Utilisez la procédure stockée système [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) pour mettre à jour la liste des langues, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b171b-110">Use the [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) system stored procedure to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages';   
    ```  
  
### <a name="to-unregister-uninstalled-word-breakers-and-filters"></a><span data-ttu-id="b171b-111">Pour annuler l'inscription des analyseurs lexicaux et des filtres désinstallés</span><span class="sxs-lookup"><span data-stu-id="b171b-111">To unregister uninstalled word breakers and filters</span></span>  
  
1.  <span data-ttu-id="b171b-112">Utilisez **sp_fulltext_service** pour mettre à jour la liste des langues, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b171b-112">Use the **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages'  
    ```  
  
2.  <span data-ttu-id="b171b-113">Utilisez **sp_fulltext_service** pour redémarrer les processus hôtes de démon de filtre (fdhost.exe), comme suit :</span><span class="sxs-lookup"><span data-stu-id="b171b-113">Use the **sp_fulltext_service** to restart the filter daemon host processes (fdhost.exe), as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'restart_all_fdhosts';  
    ```  
  
### <a name="to-replace-existing-word-breakers-or-filters-when-installing-new-ones"></a><span data-ttu-id="b171b-114">Pour remplacer les analyseurs lexicaux ou les filtres existants et en installer de nouveaux</span><span class="sxs-lookup"><span data-stu-id="b171b-114">To replace existing word breakers or filters when installing new ones</span></span>  
  
1.  <span data-ttu-id="b171b-115">Lorsque vous préparez l'installation d'un fichier DLL qui contient de nouveaux analyseurs lexicaux ou filtres, assurez-vous que son nom est différent des noms de fichiers DLL existants installés sur votre instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="b171b-115">When preparing to install a DLL file that contains new word breakers or filters, verify that it has a different filename from any of the existing DLL files installed on your server instance.</span></span>  
  
2.  <span data-ttu-id="b171b-116">Copiez le nouveau fichier .dll dans le répertoire qui contient les fichiers DDL [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] standard pour l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="b171b-116">Copy the new DLL file into the directory containing the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files for the server instance.</span></span> <span data-ttu-id="b171b-117">L’emplacement par défaut est :</span><span class="sxs-lookup"><span data-stu-id="b171b-117">The default location is:</span></span>  
  
     <span data-ttu-id="b171b-118">C:\Program Files\Microsoft SQL Server\MSSQL13.*nom_instance*\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="b171b-118">C:\Program Files\Microsoft SQL Server\MSSQL.*instance_name*\MSSQL\Binn</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b171b-119">Il est fortement recommandé de charger uniquement des composants signés et vérifiés.</span><span class="sxs-lookup"><span data-stu-id="b171b-119">We highly recommend that you load only signed and verified components.</span></span> <span data-ttu-id="b171b-120">Nous vous recommandons également d'exécuter le service de lancement FDHOST (MSSQLFDLauncher) avec le moins de privilèges possibles.</span><span class="sxs-lookup"><span data-stu-id="b171b-120">Also, we recommend that you run the FDHOST Launcher (MSSQLFDLauncher) Service with the least possible privileges.</span></span>  
  
3.  <span data-ttu-id="b171b-121">Installez les nouveaux analyseurs lexicaux ou filtres.</span><span class="sxs-lookup"><span data-stu-id="b171b-121">Install the new word breaker or filters.</span></span>  
  
     <span data-ttu-id="b171b-122">**Pour installer et charger des filtres Microsoft Filter Pack IFilters**</span><span class="sxs-lookup"><span data-stu-id="b171b-122">**To install and load Microsoft Filter Pack IFilters**</span></span>  
  
    -   [<span data-ttu-id="b171b-123">Procédure : inscrire des filtres Microsoft Filter Pack IFilters avec SQL Server</span><span class="sxs-lookup"><span data-stu-id="b171b-123">How to register Microsoft Filter Pack IFilters with SQL Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=130439)  
  
4.  <span data-ttu-id="b171b-124">Utilisez **sp_fulltext_service** pour charger les filtres et les analyseurs lexicaux récemment installés dans l’instance de serveur, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b171b-124">Use **sp_fulltext_service** to load newly installed word breakers and filters in the server instance, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service @action='load_os_resources', @value=1;  
    ```  
  
5.  <span data-ttu-id="b171b-125">Utilisez **sp_fulltext_service** pour mettre à jour la liste des langues, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b171b-125">Use **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'update_languages';  
    ```  
  
6.  <span data-ttu-id="b171b-126">Redémarrez les processus hôtes de démon de filtre (fdhost.exe) à l’aide de **sp_fulltext_service** , comme suit :</span><span class="sxs-lookup"><span data-stu-id="b171b-126">Restart the filter daemon host processes (fdhost.exe), using **sp_fulltext_service** as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'restart_all_fdhosts';   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b171b-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b171b-127">See Also</span></span>  
 <span data-ttu-id="b171b-128">[Définir le compte du service du Lanceur de démon de filtre de texte intégral](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="b171b-128">[Set the Service Account for the Full-text Filter Daemon Launcher](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="b171b-129">[Configurer et gérer des filtres pour la recherche](configure-and-manage-filters-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="b171b-129">[Configure and Manage Filters for Search](configure-and-manage-filters-for-search.md) </span></span>  
 [<span data-ttu-id="b171b-130">Configurer et gérer les analyseurs lexicaux et générateurs de formes dérivées pour la recherche</span><span class="sxs-lookup"><span data-stu-id="b171b-130">Configure and Manage Word Breakers and Stemmers for Search</span></span>](configure-and-manage-word-breakers-and-stemmers-for-search.md)  
  
  
