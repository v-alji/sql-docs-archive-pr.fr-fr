---
title: Créer la stratégie Désactivé par défaut | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 98fde3c5-297c-4d95-981e-95700bbf5ccd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16d0893c155627a41149263b5ce7b21a4a217b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601418"
---
# <a name="create-the-off-by-default-policy"></a><span data-ttu-id="48148-102">Créer la stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="48148-102">Create the Off By Default Policy</span></span>
  <span data-ttu-id="48148-103">Cette tâche crée une condition nommée Courrier désactivé basée sur la facette Configuration de la surface d'exposition.</span><span class="sxs-lookup"><span data-stu-id="48148-103">This task creates a condition named Mail Off that is based on the Surface Area Configuration facet.</span></span> <span data-ttu-id="48148-104">Ensuite, elle crée une stratégie nommée Désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="48148-104">Then, it creates a policy named Off By Default.</span></span>  
  
### <a name="to-create-the-mail-off-condition"></a><span data-ttu-id="48148-105">Pour créer la condition Courrier désactivé</span><span class="sxs-lookup"><span data-stu-id="48148-105">To create the Mail Off condition</span></span>  
  
1.  <span data-ttu-id="48148-106">Dans l’Explorateur d’objets, développez **Gestion**, **Gestion de la stratégie**, **Facettes**, cliquez avec le bouton droit sur **Configuration de la surface d’exposition**, puis cliquez sur **Nouvelle condition**.</span><span class="sxs-lookup"><span data-stu-id="48148-106">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Facets**, right-click **Surface Area Configuration**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="48148-107">Dans la boîte de dialogue **Créer une nouvelle condition** , dans la zone **Nom** , tapez **Mail Off**.</span><span class="sxs-lookup"><span data-stu-id="48148-107">In the **Create New Condition** dialog box, in the **Name** box, type **Mail Off**.</span></span>  
  
3.  <span data-ttu-id="48148-108">Dans la zone **Facette** , vérifiez que la facette **Configuration de la surface d’exposition** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="48148-108">In the **Facet** box, confirm that **Surface Area Configuration** facet is selected.</span></span>  
  
4.  <span data-ttu-id="48148-109">Dans la zone **Expression**, dans la zone **Champ**, sélectionnez **\@DatabaseMailEnabled** ; ensuite, dans la zone **Opérateur**, sélectionnez **=**  ; enfin, dans **Valeur**, sélectionnez **Faux**.</span><span class="sxs-lookup"><span data-stu-id="48148-109">In the **Expression** area, in the **Field** box, select **\@DatabaseMailEnabled**, in the **Operator** box select **=**, and in the **Value** select **False**.</span></span>  
  
5.  <span data-ttu-id="48148-110">Dans la page **Description** , entrez une description de la condition, puis cliquez sur **OK** pour créer la condition.</span><span class="sxs-lookup"><span data-stu-id="48148-110">On the **Description** page, type a description of the condition, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-off-by-default-policy"></a><span data-ttu-id="48148-111">Pour créer la stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="48148-111">To create the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="48148-112">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur **Configuration de la surface d’exposition**, puis cliquez sur **Nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="48148-112">In Object Explorer, right-click **Surface Area Configuration**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="48148-113">Dans la boîte de dialogue **Créer une nouvelle stratégie** , dans la zone **Nom** , tapez **Off By Default**.</span><span class="sxs-lookup"><span data-stu-id="48148-113">In the **Create New Policy** dialog box, in the **Name** box, type **Off By Default**.</span></span>  
  
3.  <span data-ttu-id="48148-114">Laissez la case **Activé** décochée.</span><span class="sxs-lookup"><span data-stu-id="48148-114">Leave the **Enabled** checkbox unchecked.</span></span> <span data-ttu-id="48148-115">La case à cocher **Activé** s’applique aux stratégies automatisées ; cette stratégie sera exécutée à la demande.</span><span class="sxs-lookup"><span data-stu-id="48148-115">The **Enabled** checkbox applies to automated policies, and this policy will be executed on demand.</span></span>  
  
4.  <span data-ttu-id="48148-116">Dans la case à cocher **Vérifier la condition** , faites défiler la liste jusqu’à la zone **Configuration de la surface d’exposition** , puis sélectionnez **Mail Off** comme condition à vérifier.</span><span class="sxs-lookup"><span data-stu-id="48148-116">In the **Check condition** checkbox, scroll down to the **Surface Area Configuration** area, and then select **Mail Off** as the condition to check.</span></span>  
  
5.  <span data-ttu-id="48148-117">La zone **Par rapport aux cibles** est vide car il s’agit d’une stratégie dont l’étendue est le serveur.</span><span class="sxs-lookup"><span data-stu-id="48148-117">The **Against targets** box will be blank because this is a server-scoped policy.</span></span>  
  
6.  <span data-ttu-id="48148-118">Dans la case à cocher **Mode d’évaluation** , sélectionnez **À la demande** .</span><span class="sxs-lookup"><span data-stu-id="48148-118">In the **Evaluation Mode** checkbox, select **On demand** as the evaluation mode.</span></span>  
  
7.  <span data-ttu-id="48148-119">Dans la case à cocher **Restriction sur le serveur** , sélectionnez **Aucune**.</span><span class="sxs-lookup"><span data-stu-id="48148-119">In the **Server restriction** checkbox, select **None**.</span></span>  
  
8.  <span data-ttu-id="48148-120">Dans la page **Description** , tapez une description de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="48148-120">On the **Description** page, type a description of the policy.</span></span>  
  
9. <span data-ttu-id="48148-121">Vous pouvez fournir un lien hypertexte vers une page web pour vos stratégies dans la zone **Lien hypertexte d’aide supplémentaire** .</span><span class="sxs-lookup"><span data-stu-id="48148-121">You can provide a hyperlink to a Web page for your policies in the **Additional help hyperlink** area.</span></span> <span data-ttu-id="48148-122">Dans la zone **Texte à afficher** , tapez le texte du lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="48148-122">In the **Text to display** box, type the text that will appear for the hyperlink.</span></span>  
  
10. <span data-ttu-id="48148-123">Dans la zone **Adresse** , tapez un lien hypertexte vers une page d’aide, par exemple la page d’accueil du service informatique de votre société.</span><span class="sxs-lookup"><span data-stu-id="48148-123">In the **Address** box, type a hyperlink to a Help page, such as the home page for the IT department of your company.</span></span>  
  
11. <span data-ttu-id="48148-124">Pour vérifier l’adresse en ouvrant la page web, cliquez sur **Lien de test**.</span><span class="sxs-lookup"><span data-stu-id="48148-124">To confirm the address by opening the Web page, click **Test Link**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="48148-125">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="48148-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="48148-126">Configurer un serveur pour exécuter la stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="48148-126">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
  
