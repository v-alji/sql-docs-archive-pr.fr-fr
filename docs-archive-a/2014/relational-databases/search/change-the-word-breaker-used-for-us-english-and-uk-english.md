---
title: Modifier l’analyseur lexical utilisé pour l’anglais des États-Unis et l’anglais (R.U.) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: 6b5d2177-db98-47f5-b32e-4b80a2f74ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3b759b90ec834dcb666f7862bfba3857f2fea0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610574"
---
# <a name="change-the-word-breaker-used-for-us-english-and-uk-english"></a><span data-ttu-id="1c209-102">Modifier l'analyseur lexical utilisé pour l'anglais des États-Unis et l'anglais (R.U.)</span><span class="sxs-lookup"><span data-stu-id="1c209-102">Change the Word Breaker Used for US English and UK English</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="1c209-103">installe une nouvelle version (version 14.0.4999.1038) de l’analyseur lexical et du générateur de formes dérivées pour la langue anglaise, en remplaçant la version précédente de ces composants (version 12.0.6828.0).</span><span class="sxs-lookup"><span data-stu-id="1c209-103">installs a new version (version 14.0.4999.1038) of the word breaker and stemmer for the English language, replacing the previous version of these components (version 12.0.6828.0).</span></span> <span data-ttu-id="1c209-104">Pour plus d’informations sur la modification du comportement des nouveaux composants, consultez [Changements de comportement pour la recherche en texte intégral](full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="1c209-104">For information about the changed behavior of the new components, see [Behavior Changes to Full-Text Search](full-text-search.md).</span></span> <span data-ttu-id="1c209-105">Cette rubrique décrit comment passer de la nouvelle version de ces composants à la version précédente, ou de la version précédente à la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="1c209-105">This topic describes how to switch from the new version of these components to the previous version, or to switch back from the previous version to the new version.</span></span> <span data-ttu-id="1c209-106">Pour les installations de cluster, ces modifications doivent être apportées sur tous les nœuds principaux et passifs.</span><span class="sxs-lookup"><span data-stu-id="1c209-106">For cluster installations, these changes should be made on all the primary and passive nodes.</span></span>  
  
 <span data-ttu-id="1c209-107">Les versions précédentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisaient des analyseurs lexicaux différents représentés par des CLSID différents pour l'anglais des États-Unis (LCID 1033) et l'anglais du Royaume-Uni (LCID 2057).</span><span class="sxs-lookup"><span data-stu-id="1c209-107">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] used different word breakers represented by different CLSIDs for US English (LCID 1033) and UK English (LCID 2057).</span></span> <span data-ttu-id="1c209-108">Dans cette version, les deux LCID utilisent les mêmes composants avec le même CLSID, comme indiqué dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="1c209-108">In this release, both LCIDs use the same components with the same CLSIDs, as shown in the following table:</span></span>  
  
|<span data-ttu-id="1c209-109">LCID</span><span class="sxs-lookup"><span data-stu-id="1c209-109">LCID</span></span>|<span data-ttu-id="1c209-110">Analyseur lexical installé par les versions précédentes</span><span class="sxs-lookup"><span data-stu-id="1c209-110">Word breaker installed by previous versions</span></span><br /><br /> <span data-ttu-id="1c209-111">version 12.0.6828.0</span><span class="sxs-lookup"><span data-stu-id="1c209-111">version 12.0.6828.0</span></span>|<span data-ttu-id="1c209-112">Générateur de formes dérivées installé par les versions précédentes</span><span class="sxs-lookup"><span data-stu-id="1c209-112">Stemmer installed by previous versions</span></span>|<span data-ttu-id="1c209-113">Analyseur lexical installé par cette version</span><span class="sxs-lookup"><span data-stu-id="1c209-113">Word breaker installed by this version</span></span><br /><br /> <span data-ttu-id="1c209-114">version 14.0.4999.1038</span><span class="sxs-lookup"><span data-stu-id="1c209-114">version 14.0.4999.1038</span></span>|<span data-ttu-id="1c209-115">Générateur de formes dérivées installé par cette version</span><span class="sxs-lookup"><span data-stu-id="1c209-115">Stemmer installed by this version</span></span>|  
|----------|-------------------------------------------------------------------------|--------------------------------------------|-----------------------------------------------------------------------|---------------------------------------|  
|<span data-ttu-id="1c209-116">1033</span><span class="sxs-lookup"><span data-stu-id="1c209-116">1033</span></span><br /><span data-ttu-id="1c209-117">(Anglais des États-Unis)</span><span class="sxs-lookup"><span data-stu-id="1c209-117">(US English)</span></span>|<span data-ttu-id="1c209-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span><span class="sxs-lookup"><span data-stu-id="1c209-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span></span>|<span data-ttu-id="1c209-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="1c209-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="1c209-120">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="1c209-120">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="1c209-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="1c209-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
|<span data-ttu-id="1c209-122">2057</span><span class="sxs-lookup"><span data-stu-id="1c209-122">2057</span></span><br /><span data-ttu-id="1c209-123">(Anglais du Royaume-Uni)</span><span class="sxs-lookup"><span data-stu-id="1c209-123">(UK English)</span></span>|<span data-ttu-id="1c209-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span><span class="sxs-lookup"><span data-stu-id="1c209-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span></span>|<span data-ttu-id="1c209-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="1c209-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="1c209-126">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="1c209-126">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="1c209-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="1c209-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
  
 <span data-ttu-id="1c209-128">Les composants décrits dans cette rubrique sont des fichiers DLL installés dans le dossier `MSSQL\Binn` de l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c209-128">The components described in this topic are DLL files that are installed in the `MSSQL\Binn` folder for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="1c209-129">Le chemin complet est généralement `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span><span class="sxs-lookup"><span data-stu-id="1c209-129">The full path is typically `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span></span>  
  
 <span data-ttu-id="1c209-130">Pour plus d’informations sur les analyseurs lexicaux et générateurs de formes dérivées, consultez [Configurer et gérer les analyseurs lexicaux et générateurs de formes dérivées pour la recherche](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span><span class="sxs-lookup"><span data-stu-id="1c209-130">For more information about word breakers and stemmers, see [Configure and Manage Word Breakers and Stemmers for Search](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="switching-from-the-current-english-word-breaker-to-the-previous-english-word-breakers"></a><span data-ttu-id="1c209-131">Basculement de l'analyseur lexical anglais actuel vers les analyseurs lexicaux anglais précédents</span><span class="sxs-lookup"><span data-stu-id="1c209-131">Switching from the current English word breaker to the previous English word breakers</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-us-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="1c209-132">Pour basculer de la version actuelle de l'analyseur lexical anglais des États-Unis vers la version précédente</span><span class="sxs-lookup"><span data-stu-id="1c209-132">To switch from the current version of the US English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="1c209-133">Dans le Registre, accédez au nœud suivant : **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<racine_instance\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="1c209-133">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="1c209-134">Procédez comme suit pour ajouter de nouvelles clés pour les COM ClassID des interfaces précédentes de l'analyseur lexical et du générateur de formes dérivées anglais des États-Unis pour LCID 1033 :</span><span class="sxs-lookup"><span data-stu-id="1c209-134">Use the following steps to add new keyS for the COM ClassIDs for the previous US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="1c209-135">Ajoutez une nouvelle clé avec la valeur **{188D6CC5-CB03-4C01-912E-47D21295D77E}** pour l’analyseur lexical précédent.</span><span class="sxs-lookup"><span data-stu-id="1c209-135">Add a new key with the value **{188D6CC5-CB03-4C01-912E-47D21295D77E}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="1c209-136">Mettez à jour les données (valeurs par défaut) de cette valeur de clé en la définissant sur **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="1c209-136">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="1c209-137">Ajoutez une nouvelle clé avec la valeur **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** pour le générateur de formes dérivées précédent.</span><span class="sxs-lookup"><span data-stu-id="1c209-137">Add a new key with the value **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="1c209-138">Mettez à jour les données (valeurs par défaut) de cette valeur de clé en la définissant sur **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="1c209-138">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="1c209-139">Dans le Registre, accédez au nœud suivant : **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<RacineInstance\>\MSSearch\Language\enu**.</span><span class="sxs-lookup"><span data-stu-id="1c209-139">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\enu**.</span></span>  
  
4.  <span data-ttu-id="1c209-140">Mettez à jour la valeur de clé **WBreakerClass** en la remplaçant par **{188D6CC5-CB03-4C01-912E-47D21295D77E}** .</span><span class="sxs-lookup"><span data-stu-id="1c209-140">Update the **WBreakerClass** key value to **{188D6CC5-CB03-4C01-912E-47D21295D77E}**.</span></span>  
  
5.  <span data-ttu-id="1c209-141">Mettez à jour la valeur de clé **StemmerClass** en la remplaçant par **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="1c209-141">Update the **StemmerClass** key value to **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="1c209-142">Redémarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c209-142">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-uk-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="1c209-143">Pour basculer de la version actuelle de l'analyseur lexical anglais (R.U.) vers la version précédente</span><span class="sxs-lookup"><span data-stu-id="1c209-143">To switch from the current version of the UK English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="1c209-144">Dans le Registre, accédez au nœud suivant : **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<racine_instance\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="1c209-144">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="1c209-145">Procédez comme suit pour ajouter une nouvelle clé pour les COM ClassID des interfaces précédentes de l'analyseur lexical et du générateur de formes dérivées anglais (R.U.) pour LCID 2057 :</span><span class="sxs-lookup"><span data-stu-id="1c209-145">Use the following steps to add a new key for the COM ClassIDs for the previous UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="1c209-146">Ajoutez une nouvelle clé avec la valeur **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** pour l’analyseur lexical précédent.</span><span class="sxs-lookup"><span data-stu-id="1c209-146">Add a new key with the value **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="1c209-147">Mettez à jour les données (valeurs par défaut) de cette valeur de clé en la définissant sur **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="1c209-147">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="1c209-148">Ajoutez une nouvelle clé avec la valeur **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** pour le générateur de formes dérivées précédent.</span><span class="sxs-lookup"><span data-stu-id="1c209-148">Add a new key with the value **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="1c209-149">Mettez à jour les données (valeurs par défaut) de cette valeur de clé en la définissant sur **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="1c209-149">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="1c209-150">Dans le Registre, accédez au nœud suivant : **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<racine_instance\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="1c209-150">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="1c209-151">Mettez à jour la valeur de clé **WBreakerClass** en la remplaçant par **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** .</span><span class="sxs-lookup"><span data-stu-id="1c209-151">Update the **WBreakerClass** key value to **{173C97E2-AEBE-437C-9445-01B237ABF2F6}**.</span></span>  
  
5.  <span data-ttu-id="1c209-152">Mettez à jour la valeur de clé **StemmerClass** en la remplaçant par **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="1c209-152">Update the **StemmerClass** key value to **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="1c209-153">Redémarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c209-153">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="switching-back-from-the-previous-english-word-breakers-to-the-current-english-word-breaker"></a><span data-ttu-id="1c209-154">Rebasculement des analyseurs lexicaux anglais précédents vers l'analyseur lexical anglais actuel</span><span class="sxs-lookup"><span data-stu-id="1c209-154">Switching back from the previous English word breakers to the current English word breaker</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-us-english-word-breaker-to-the-current-version"></a><span data-ttu-id="1c209-155">Pour rebasculer de la version précédente de l'analyseur lexical anglais des États-Unis vers la version actuelle</span><span class="sxs-lookup"><span data-stu-id="1c209-155">To switch back from the previous version of the US English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="1c209-156">Dans le Registre, accédez au nœud suivant : **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<racine_instance\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="1c209-156">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="1c209-157">Si les clés suivantes n'existent pas, procédez comme suit pour ajouter une nouvelle clé pour les COM ClassID des interfaces actuelles de l'analyseur lexical et du générateur de formes dérivées anglais des États-Unis pour LCID 1033 :</span><span class="sxs-lookup"><span data-stu-id="1c209-157">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="1c209-158">Ajoutez une nouvelle clé dont la valeur est **{9faed859-0b30-4434-ae65-412e14a16fb8}** pour l’analyseur lexical actuel.</span><span class="sxs-lookup"><span data-stu-id="1c209-158">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="1c209-159">Mettez à jour les données (valeurs par défaut) de cette valeur de clé en la définissant sur **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="1c209-159">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="1c209-160">Ajoutez une nouvelle clé dont la valeur est **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** pour le générateur de formes dérivées actuel.</span><span class="sxs-lookup"><span data-stu-id="1c209-160">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="1c209-161">Mettez à jour les données (valeurs par défaut) de cette valeur de clé en la définissant sur **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="1c209-161">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="1c209-162">Dans le Registre, accédez au nœud suivant : **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<racine_instance\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="1c209-162">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="1c209-163">Mettez à jour la valeur de clé **WBreakerClass** en la définissant sur **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="1c209-163">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="1c209-164">Mettez à jour la valeur de clé **StemmerClass** en la définissant sur **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="1c209-164">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="1c209-165">Redémarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c209-165">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-uk-english-word-breaker-to-the-current-version"></a><span data-ttu-id="1c209-166">Pour rebasculer de la version précédente de l'analyseur lexical anglais (R.U.) vers la version actuelle</span><span class="sxs-lookup"><span data-stu-id="1c209-166">To switch back from the previous version of the UK English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="1c209-167">Dans le Registre, accédez au nœud suivant : **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<racine_instance\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="1c209-167">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="1c209-168">Si les clés suivantes n'existent pas, procédez comme suit pour ajouter une nouvelle clé pour les COM ClassID des interfaces actuelles de l'analyseur lexical et du générateur de formes dérivées anglais (R.U.) pour LCID 2057 :</span><span class="sxs-lookup"><span data-stu-id="1c209-168">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="1c209-169">Ajoutez une nouvelle clé dont la valeur est **{9faed859-0b30-4434-ae65-412e14a16fb8}** pour l’analyseur lexical actuel.</span><span class="sxs-lookup"><span data-stu-id="1c209-169">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="1c209-170">Mettez à jour les données (valeurs par défaut) de cette valeur de clé en la définissant sur **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="1c209-170">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="1c209-171">Ajoutez une nouvelle clé dont la valeur est **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** pour le générateur de formes dérivées actuel.</span><span class="sxs-lookup"><span data-stu-id="1c209-171">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="1c209-172">Mettez à jour les données (valeurs par défaut) de cette valeur de clé en la définissant sur **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="1c209-172">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="1c209-173">Dans le Registre, accédez au nœud suivant : **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<racine_instance\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="1c209-173">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="1c209-174">Mettez à jour la valeur de clé **WBreakerClass** en la définissant sur **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="1c209-174">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="1c209-175">Mettez à jour la valeur de clé **StemmerClass** en la définissant sur **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="1c209-175">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="1c209-176">Redémarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c209-176">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c209-177">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c209-177">See Also</span></span>  
 <span data-ttu-id="1c209-178">[Rétablir la version précédente des analyseurs lexicaux utilisés par la recherche](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span><span class="sxs-lookup"><span data-stu-id="1c209-178">[Revert the Word Breakers Used by Search to the Previous Version](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span></span>  
 [<span data-ttu-id="1c209-179">Changements de comportement de la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="1c209-179">Behavior Changes to Full-Text Search</span></span>](full-text-search.md)  
  
  
