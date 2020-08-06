---
title: Versions linguistiques locales dans SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 20b99363-0490-4aa3-9a3d-262f827d81e8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646ffaed1e4b709c2c26030379f0a7f223f221e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697396"
---
# <a name="local-language-versions-in-sql-server"></a><span data-ttu-id="52e45-102">Versions linguistiques locales dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="52e45-102">Local Language Versions in SQL Server</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="52e45-103">prend en charge toutes les langues prises en charge par les systèmes d'exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="52e45-103">supports all languages that are supported by Windows operating systems.</span></span>  
  
## <a name="cross-language-support"></a><span data-ttu-id="52e45-104">Prise en charge de langues différentes</span><span class="sxs-lookup"><span data-stu-id="52e45-104">Cross-Language Support</span></span>  
  
-   <span data-ttu-id="52e45-105">La version anglaise de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est prise en charge sur toutes les versions localisées des systèmes d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="52e45-105">The English-language version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is supported on all localized versions of operating systems.</span></span>  
  
-   <span data-ttu-id="52e45-106">Les versions localisées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont prises en charge sur les systèmes d'exploitation localisés dans la langue correspondante ou sur les versions anglaises des systèmes d'exploitation pris en charge grâce aux paramètres du Pack Windows d'interface utilisateur multilingue.</span><span class="sxs-lookup"><span data-stu-id="52e45-106">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on localized operating systems with the corresponding language or on English-language versions of supported operating systems by using the Windows Multilingual User Interface Pack (MUI) settings.</span></span> <span data-ttu-id="52e45-107">Pour plus d'informations, voir [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span><span class="sxs-lookup"><span data-stu-id="52e45-107">For more information, see [Configure Operating System to Support Localized Versions](../../../2014/sql-server/install/local-language-versions-in-sql-server.md#BK_ConfigureOS).</span></span>  
  
-   <span data-ttu-id="52e45-108">Les versions localisées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent être mises à niveau uniquement vers des versions localisées dans la même langue et ne peuvent pas être mises à niveau vers la version anglaise.</span><span class="sxs-lookup"><span data-stu-id="52e45-108">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can only be upgraded to localized versions of the same language, and cannot be upgraded to the English-language version.</span></span>  
  
-   <span data-ttu-id="52e45-109">Les versions localisées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent également être installées côte à côte avec des instances en langue anglaise de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52e45-109">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can also be installed side by side with English-language instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="configure-operating-system-to-support-localized-versions"></a><a name="BK_ConfigureOS"></a> <span data-ttu-id="52e45-110">Configure Operating System to Support Localized Versions</span><span class="sxs-lookup"><span data-stu-id="52e45-110">Configure Operating System to Support Localized Versions</span></span>  
 <span data-ttu-id="52e45-111">Les versions localisées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont prises en charge dans les versions anglaises des systèmes d'exploitation pris en charge via l'utilisation des paramètres du Pack d'interface utilisateur multilingue de Windows (MUI, Multilingual User Interface).</span><span class="sxs-lookup"><span data-stu-id="52e45-111">Localized versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are supported on English-language versions of supported operating systems through the use of Windows Multilingual User Interface Pack (MUI) settings.</span></span>  
  
 <span data-ttu-id="52e45-112">Vous devez toutefois vérifier certains paramètres de système d'exploitation avant d'installer une version localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un serveur qui exécute un système d'exploitation en langue anglaise avec un paramétrage MUI non anglais.</span><span class="sxs-lookup"><span data-stu-id="52e45-112">However, you must verify certain operating system settings before installing a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a server that is running an English-language operating system with a non-English MUI setting.</span></span> <span data-ttu-id="52e45-113">Vous devez vérifier que les paramètres de système d'exploitation suivants correspondent à la langue de la version localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui va être installée.</span><span class="sxs-lookup"><span data-stu-id="52e45-113">You need to verify that the following operating system settings match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed:</span></span>  
  
-   <span data-ttu-id="52e45-114">Le paramètre de l'interface utilisateur du système d'exploitation</span><span class="sxs-lookup"><span data-stu-id="52e45-114">The operating system user interface setting</span></span>  
  
-   <span data-ttu-id="52e45-115">Les paramètres régionaux utilisateur du système d'exploitation</span><span class="sxs-lookup"><span data-stu-id="52e45-115">The operating system user locale setting</span></span>  
  
-   <span data-ttu-id="52e45-116">Les paramètres régionaux système</span><span class="sxs-lookup"><span data-stu-id="52e45-116">The system locale setting</span></span>  
  
 <span data-ttu-id="52e45-117">Si les paramètres ne correspondent pas à la langue de la version localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à installer, procédez comme suit pour définir correctement ces paramètres de système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="52e45-117">If the settings do not match the language of the localized [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be installed, then use the following procedures to correctly set these operating system settings.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="52e45-118">Les installations de différentes versions linguistiques d'instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur le même ordinateur ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="52e45-118">Installations of different language versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances on the same computer are not supported.</span></span>  
  
#### <a name="to-change-the-operating-system-user-interface-setting"></a><span data-ttu-id="52e45-119">Pour modifier le paramètre de l'interface utilisateur du système d'exploitation</span><span class="sxs-lookup"><span data-stu-id="52e45-119">To change the operating system user interface setting</span></span>  
  
1.  <span data-ttu-id="52e45-120">Si elle n'est pas déjà installée, installez l'interface utilisateur multilingue du système d'exploitation qui correspond à votre version localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52e45-120">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="52e45-121">Dans le Panneau de configuration, ouvrez **Options régionales et linguistiques**.</span><span class="sxs-lookup"><span data-stu-id="52e45-121">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="52e45-122">Dans l'onglet **Langues** , pour **Langue utilisée dans les menus et les dialogues**, sélectionnez une valeur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="52e45-122">On the **Languages** tab, for **Language used in menus and dialogs**, select a value from the list.</span></span>  
  
     <span data-ttu-id="52e45-123">Ce paramètre affecte la langue de l'interface utilisateur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]qui doit correspondre à votre version localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52e45-123">This setting will affect the user interface language of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so it must match your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="52e45-124">Cliquez sur **Appliquer** pour confirmer la modification et sur **OK** pour fermer la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="52e45-124">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-operating-system-user-locale-setting"></a><span data-ttu-id="52e45-125">Pour modifier les paramètres régionaux utilisateur du système d'exploitation</span><span class="sxs-lookup"><span data-stu-id="52e45-125">To change the operating system user locale setting</span></span>  
  
1.  <span data-ttu-id="52e45-126">Si elle n'est pas déjà installée, installez l'interface utilisateur multilingue du système d'exploitation qui correspond à votre version localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52e45-126">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="52e45-127">Dans le Panneau de configuration, ouvrez **Options régionales et linguistiques**.</span><span class="sxs-lookup"><span data-stu-id="52e45-127">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="52e45-128">Dans l'onglet **Options régionales** , pour **Sélectionner un élément pour afficher ses paramètres**, sélectionnez une valeur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="52e45-128">On the **Regional Options** tab, for **Select an item to match its preferences**, select a value from the list.</span></span>  
  
     <span data-ttu-id="52e45-129">Ce paramètre affecte la mise en forme des données propre à une culture spécifique.</span><span class="sxs-lookup"><span data-stu-id="52e45-129">This setting will affect culture-specific data formatting.</span></span>  
  
4.  <span data-ttu-id="52e45-130">Cliquez sur **Appliquer** pour confirmer la modification et sur **OK** pour fermer la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="52e45-130">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
#### <a name="to-change-the-system-locale-setting"></a><span data-ttu-id="52e45-131">Pour modifier les paramètres régionaux système</span><span class="sxs-lookup"><span data-stu-id="52e45-131">To change the system locale setting</span></span>  
  
1.  <span data-ttu-id="52e45-132">Si elle n'est pas déjà installée, installez l'interface utilisateur multilingue du système d'exploitation qui correspond à votre version localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52e45-132">If not already installed, install the operating system MUI that matches your localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="52e45-133">Dans le Panneau de configuration, ouvrez **Options régionales et linguistiques**.</span><span class="sxs-lookup"><span data-stu-id="52e45-133">In Control Panel, open **Regional and Language Options**.</span></span>  
  
3.  <span data-ttu-id="52e45-134">Sous l’onglet **Options avancées** , pour **Sélectionnez une langue qui corresponde à la version des programmes non Unicode que vous voulez utiliser**, sélectionnez une valeur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="52e45-134">On the **Advanced** tab, for **Select a language to match the language version of the non-Unicode programs you want to use**, select a value from the list.</span></span>  
  
     <span data-ttu-id="52e45-135">Ce paramètre permet au programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de choisir le meilleur classement par défaut pour votre installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52e45-135">This setting will allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to choose the best default collation for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
4.  <span data-ttu-id="52e45-136">Cliquez sur **Appliquer** pour confirmer la modification et sur **OK** pour fermer la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="52e45-136">Click **Apply** to confirm the change, and **OK** to close the window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e45-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52e45-137">See Also</span></span>  
 <span data-ttu-id="52e45-138">[Configurations matérielle et logicielle requises pour l’installation de SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52e45-138">[Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md) </span></span>  
 [<span data-ttu-id="52e45-139">Installer SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="52e45-139">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
