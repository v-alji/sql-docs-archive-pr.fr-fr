---
title: Choisir le bon compte de service SQL Server Agent pour les environnements multiserveurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- multiserver environments [SQL Server], SQL Server Agent service account behavior
ms.assetid: a07e2f38-281c-495b-965b-13fad03ba548
author: stevestein
ms.author: sstein
ms.openlocfilehash: 94ef890f5d2ef2b85d2f4d1023a93747e903a7f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614336"
---
# <a name="choose-the-right-sql-server-agent-service-account-for-multiserver-environments"></a><span data-ttu-id="541da-102">Choisir le compte de service SQL Server Agent correct pour les environnements multiserveurs</span><span class="sxs-lookup"><span data-stu-id="541da-102">Choose the Right SQL Server Agent Service Account for Multiserver Environments</span></span>
  <span data-ttu-id="541da-103">Le compte Windows que vous choisissez pour le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent peut affecter le comportement d'un environnement multiserveur de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="541da-103">The Windows account you choose for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can affect the behavior of a multiserver environment, as follows:</span></span>  
  
-   <span data-ttu-id="541da-104">Si vous exécutez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent avec un compte n'appartenant pas au groupe Administrateurs local de Windows, l'inscription des serveurs cibles en serveurs maîtres risque d'échouer.</span><span class="sxs-lookup"><span data-stu-id="541da-104">If you run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service under an account that is not a member of the local Windows Administrators group, enlisting target servers to master servers may fail.</span></span> <span data-ttu-id="541da-105">Si tel est le cas, le message d'erreur suivant apparaît :</span><span class="sxs-lookup"><span data-stu-id="541da-105">If it does, the following error message is returned:</span></span>  
  
     <span data-ttu-id="541da-106">« Échec de l'inscription ».</span><span class="sxs-lookup"><span data-stu-id="541da-106">"The enlistment operation failed."</span></span>  
  
     <span data-ttu-id="541da-107">Redémarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pour résoudre ce problème.</span><span class="sxs-lookup"><span data-stu-id="541da-107">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services to resolve this issue.</span></span>  
  
-   <span data-ttu-id="541da-108">Lorsque vous exécutez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent avec le compte système local, les opérations de serveur maître/serveur cible sont prises en charge uniquement si les serveurs maître et cible résident sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="541da-108">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is run under the Local System account, master server-target server operations are supported only if both the master server and the target server reside on the same computer.</span></span> <span data-ttu-id="541da-109">Si vous optez pour cette configuration, le message suivant apparaît lorsque vous inscrivez des serveurs cibles sur un serveur maître :</span><span class="sxs-lookup"><span data-stu-id="541da-109">If you use this configuration, the following message is returned when you enlist target servers to a master server:</span></span>  
  
     <span data-ttu-id="541da-110">« Vérifiez que le compte de démarrage de l’agent pour *<nom_ordinateur_serveur_cible>* dispose des autorisations pour se connecter en tant que serveur cible. »</span><span class="sxs-lookup"><span data-stu-id="541da-110">"Ensure the agent start-up account for *<target_server_computer_name>* has rights to log on as targetServer."</span></span>  
  
     <span data-ttu-id="541da-111">Vous pouvez ignorer ce message d'information.</span><span class="sxs-lookup"><span data-stu-id="541da-111">You can ignore this informational message.</span></span> <span data-ttu-id="541da-112">L'opération d'enregistrement doit se terminer correctement.</span><span class="sxs-lookup"><span data-stu-id="541da-112">The enlistment operation should complete successfully.</span></span>  
  
 <span data-ttu-id="541da-113">Pour plus d’informations sur le choix d’un compte pour le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="541da-113">For more information about choosing an account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span>  
  
  
