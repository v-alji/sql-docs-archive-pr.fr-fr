---
title: Configurer un pare-feu pour l’accès FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- Windows Firewall [Database Engine], FILESTREAM
- FILESTREAM [SQL Server], Windows Firewall
ms.assetid: fc52007f-c26f-4f8e-b9d8-55a7978f4d56
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8b787403fefdd336dd82bf7ccb93cdf21fe5a90d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612979"
---
# <a name="configure-a-firewall-for-filestream-access"></a><span data-ttu-id="12939-102">Configurer un pare-feu pour l'accès FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="12939-102">Configure a Firewall for FILESTREAM Access</span></span>
  <span data-ttu-id="12939-103">Pour pouvoir utiliser FILESTREAM dans un environnement protégé par un pare-feu, le client et le serveur doivent être en mesure de résoudre les noms DNS sur le serveur qui contient les fichiers FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="12939-103">To use FILESTREAM in a firewall-protected environment, both the client and server must be able to resolve DNS names to the server that contains the FILESTREAM files.</span></span> <span data-ttu-id="12939-104">FILESTREAM requiert l'ouverture des ports 139 et 445 dédiés au partage de fichiers Windows.</span><span class="sxs-lookup"><span data-stu-id="12939-104">FILESTREAM requires the Windows file-sharing ports 139 and 445 to be open.</span></span>  
  
### <a name="to-open-the-windows-file-sharing-ports-on-a-computer-that-is-running-windows-7"></a><span data-ttu-id="12939-105">Pour ouvrir les ports de partage de fichiers Windows sur un ordinateur qui exécute Windows 7</span><span class="sxs-lookup"><span data-stu-id="12939-105">To open the Windows file-sharing ports on a computer that is running Windows 7</span></span>  
  
1.  <span data-ttu-id="12939-106">Dans le Panneau de configuration, ouvrez **Pare-feu Windows**.</span><span class="sxs-lookup"><span data-stu-id="12939-106">In Control Panel, open **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="12939-107">Dans le volet gauche, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="12939-107">In the left pane, click **Advanced settings**.</span></span> <span data-ttu-id="12939-108">Si vous êtes invité à entrer un mot de passe administrateur ou une confirmation, tapez le mot de passe ou confirmez.</span><span class="sxs-lookup"><span data-stu-id="12939-108">If you're prompted for an administrator password or confirmation, type the password or provide confirmation.</span></span>  
  
3.  <span data-ttu-id="12939-109">Dans la boîte de dialogue **Pare-feu Windows avec fonctions avancées de sécurité** , dans le volet gauche, cliquez sur **Règles de trafic entrant**, puis, dans le volet droit, cliquez sur **Nouvelle règle**.</span><span class="sxs-lookup"><span data-stu-id="12939-109">In the **Windows Firewall with Advanced Security** dialog box, in the left pane, click **Inbound Rules**, and then, in the right pane, click **New Rule**.</span></span>  
  
4.  <span data-ttu-id="12939-110">Suivez les instructions de l'Assistant Nouvelle règle de trafic entrant pour ajouter le port TCP 139.</span><span class="sxs-lookup"><span data-stu-id="12939-110">Follow the instructions in the New Inbound Rule wizard to add TCP port 139.</span></span>  
  
5.  <span data-ttu-id="12939-111">Répétez l'étape précédente pour ajouter le port TCP 445.</span><span class="sxs-lookup"><span data-stu-id="12939-111">Repeat the previous step to add TCP port 445.</span></span>  
  
6.  <span data-ttu-id="12939-112">Fermez la boîte de dialogue **Pare-feu Windows avec fonctions avancées de sécurité** .</span><span class="sxs-lookup"><span data-stu-id="12939-112">Close the **Windows Firewall with Advanced Security** dialog box.</span></span>  
  
  
