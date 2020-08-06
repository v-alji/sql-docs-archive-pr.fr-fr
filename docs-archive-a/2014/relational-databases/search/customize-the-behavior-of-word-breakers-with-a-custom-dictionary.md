---
title: Personnaliser le comportement des analyseurs lexicaux avec un dictionnaire personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: a8e278d1-aeaa-48f1-a0c6-5de232c983e4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9fb02a47da20134925d9b2486ea0c08091af4aa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700986"
---
# <a name="customize-the-behavior-of-word-breakers-with-a-custom-dictionary"></a><span data-ttu-id="ae7b6-102">Personnaliser le comportement des analyseurs lexicaux avec un dictionnaire personnalisé</span><span class="sxs-lookup"><span data-stu-id="ae7b6-102">Customize the Behavior of Word Breakers with a Custom Dictionary</span></span>
  <span data-ttu-id="ae7b6-103">Vous pouvez personnaliser le comportement de l'analyseur lexical pour une langue particulière en créant un fichier de dictionnaire personnalisé propre à une langue.</span><span class="sxs-lookup"><span data-stu-id="ae7b6-103">You can customize the behavior of the word breaker for a particular language by creating a language-specific custom dictionary file.</span></span> <span data-ttu-id="ae7b6-104">Par exemple, vous pouvez empêcher l'analyseur lexical de séparer certains termes ou modèles.</span><span class="sxs-lookup"><span data-stu-id="ae7b6-104">For example, you can prevent the word breaker from breaking certain terms or patterns.</span></span>  
  
 <span data-ttu-id="ae7b6-105">Pour plus d'informations, consultez l'article SharePoint suivant :</span><span class="sxs-lookup"><span data-stu-id="ae7b6-105">For more information, see the following SharePoint article:</span></span>  
  
 [<span data-ttu-id="ae7b6-106">Créer un dictionnaire personnalisé (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="ae7b6-106">Create a custom dictionary (SharePoint Server 2010)</span></span>](https://go.microsoft.com/fwlink/?LinkId=215011)  
  
 <span data-ttu-id="ae7b6-107">Pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], placez les fichiers de dictionnaire personnalisés dans le dossier suivant :</span><span class="sxs-lookup"><span data-stu-id="ae7b6-107">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], place custom dictionary files in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\<instance name>\MSSQL\Binn`  
  
 <span data-ttu-id="ae7b6-108">Après avoir créé ou modifié les fichiers de dictionnaire personnalisés, redémarrez le lanceur de démon de texte intégral SQL à l'aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ae7b6-108">After creating or changing custom dictionary files, restart the SQL Full-text Daemon Launcher with the following command:</span></span>  
  
 `exec sp_fulltext_service 'restart_all_fdhosts'`  
  
  
