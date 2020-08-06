---
title: Mots de passe forts | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], passwords
- passwords [SQL Server], strong
- symbols [SQL Server]
- security [SQL Server], passwords
- passwords [SQL Server], symbols
- characters [SQL Server], password policies
- strong passwords [SQL Server]
ms.assetid: 338548f4-c4d8-47ca-b597-5c9c0f2fa205
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5e878e0de5ee1f496dcc981182d42f5898838c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697664"
---
# <a name="strong-passwords"></a><span data-ttu-id="7c816-102">Mots de passe forts</span><span class="sxs-lookup"><span data-stu-id="7c816-102">Strong Passwords</span></span>
  <span data-ttu-id="7c816-103">Les mots de passe peuvent représenter le point le plus faible dans le déploiement de sécurité d'un serveur.</span><span class="sxs-lookup"><span data-stu-id="7c816-103">Passwords can be the weakest link in a server security deployment.</span></span> <span data-ttu-id="7c816-104">Vous devez toujours faire preuve de la plus grande attention lorsque vous choisissez un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7c816-104">You should always take great care when you select a password.</span></span> <span data-ttu-id="7c816-105">Un mot de passe fort présente les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7c816-105">A strong password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="7c816-106">il comprend au moins 8 caractères ;</span><span class="sxs-lookup"><span data-stu-id="7c816-106">Is at least 8 characters long.</span></span>  
  
-   <span data-ttu-id="7c816-107">il combine des lettres, des chiffres et des symboles ;</span><span class="sxs-lookup"><span data-stu-id="7c816-107">Combines letters, numbers, and symbol characters within the password.</span></span>  
  
-   <span data-ttu-id="7c816-108">il ne se trouve pas dans un dictionnaire ;</span><span class="sxs-lookup"><span data-stu-id="7c816-108">Is not found in a dictionary.</span></span>  
  
-   <span data-ttu-id="7c816-109">il ne correspond pas au nom d'une commande ;</span><span class="sxs-lookup"><span data-stu-id="7c816-109">Is not the name of a command.</span></span>  
  
-   <span data-ttu-id="7c816-110">il ne correspond pas au nom d'une personne ;</span><span class="sxs-lookup"><span data-stu-id="7c816-110">Is not the name of a person.</span></span>  
  
-   <span data-ttu-id="7c816-111">il ne correspond pas au nom d'un utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="7c816-111">Is not the name of a user.</span></span>  
  
-   <span data-ttu-id="7c816-112">il ne correspond pas au nom d'un ordinateur ;</span><span class="sxs-lookup"><span data-stu-id="7c816-112">Is not the name of a computer.</span></span>  
  
-   <span data-ttu-id="7c816-113">il est modifié régulièrement ;</span><span class="sxs-lookup"><span data-stu-id="7c816-113">Is changed regularly.</span></span>  
  
-   <span data-ttu-id="7c816-114">il est complètement différent des mots de passe précédents.</span><span class="sxs-lookup"><span data-stu-id="7c816-114">Is significantly different from previous passwords.</span></span>  
  
 <span data-ttu-id="7c816-115">Les mots de passe [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent compter jusqu’à 128 caractères dont des lettres, des symboles et des chiffres.</span><span class="sxs-lookup"><span data-stu-id="7c816-115">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passwords can contain up to 128 characters, including letters, symbols, and digits.</span></span> <span data-ttu-id="7c816-116">Étant donné que les noms de connexion, les noms d'utilisateurs, les rôles et les mots de passe sont souvent utilisés dans des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] , certains symboles doivent être placés entre guillemets (") ou crochets ([ ]).</span><span class="sxs-lookup"><span data-stu-id="7c816-116">Because logins, user names, roles, and passwords are frequently used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, certain symbols must be enclosed by double quotation marks (") or square brackets ([ ]).</span></span> <span data-ttu-id="7c816-117">Utilisez ces délimiteurs dans les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] lorsque le nom de connexion, le nom d'utilisateur, le rôle ou le mot de passe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] présente les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7c816-117">Use these delimiters in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login, user, role, or password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="7c816-118">il contient ou commence par un espace ;</span><span class="sxs-lookup"><span data-stu-id="7c816-118">Contains or starts with a space character.</span></span>  
  
-   <span data-ttu-id="7c816-119">il commence par le caractère $ ou \@.</span><span class="sxs-lookup"><span data-stu-id="7c816-119">Starts with the $ or \@ character.</span></span>  
  
 <span data-ttu-id="7c816-120">Un nom d’accès ou un mot de passe, s’il est utilisé dans une chaîne de connexion OLE DB ou ODBC, ne doit pas contenir les caractères suivants: [] {}() , ; ?</span><span class="sxs-lookup"><span data-stu-id="7c816-120">If used in an OLE DB or ODBC connection string, a login or password must not contain the following characters: [] {}() , ; ?</span></span> <span data-ttu-id="7c816-121">\* !</span><span class="sxs-lookup"><span data-stu-id="7c816-121">\* !</span></span> <span data-ttu-id="7c816-122">\@.</span><span class="sxs-lookup"><span data-stu-id="7c816-122">\@.</span></span> <span data-ttu-id="7c816-123">Ces caractères servent en effet à initialiser une connexion ou à séparer les valeurs de la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="7c816-123">These characters are used to either initialize a connection or separate connection values.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="7c816-124">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="7c816-124">Related Content</span></span>  
 [<span data-ttu-id="7c816-125">Stratégie de mot de passe</span><span class="sxs-lookup"><span data-stu-id="7c816-125">Password Policy</span></span>](password-policy.md)  
  
  
