---
title: Boîte de message d’exception de programme | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- exception message box [SQL Server]
- displaying exception message box
ms.assetid: c771985b-149c-459a-b3cb-7b15fde01150
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9d49bdf8c73f86b2c334018d40510b4ae67c85ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708591"
---
# <a name="program-exception-message-box"></a><span data-ttu-id="841e3-102">Programmer la boîte de message d'exceptions</span><span class="sxs-lookup"><span data-stu-id="841e3-102">Program Exception Message Box</span></span>
  <span data-ttu-id="841e3-103">Vous pouvez utiliser la boîte de message d'exception dans vos applications pour fournir un contrôle nettement supérieur sur les messages que celui fourni par la classe <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="841e3-103">You can use the exception message box in your applications to provide significantly more control over the messaging experience than is provided by the <xref:System.Windows.Forms.MessageBox> class.</span></span> <span data-ttu-id="841e3-104">Pour plus d’informations, consultez [programmation de la boîte de message d’exception](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span><span class="sxs-lookup"><span data-stu-id="841e3-104">For more information, see [Exception Message Box Programming](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span></span> <span data-ttu-id="841e3-105">Pour plus d'informations sur la façon d'obtenir et de déployer le fichier .dll de boîte de message d'exception, consultez [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span><span class="sxs-lookup"><span data-stu-id="841e3-105">For information about how to obtain and deploy the exception message box .dll, see [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="841e3-106">Procédure</span><span class="sxs-lookup"><span data-stu-id="841e3-106">Procedure</span></span>  
  
#### <a name="to-handle-an-exception-by-using-the-exception-message-box"></a><span data-ttu-id="841e3-107">Pour gérer une exception en utilisant la boîte de message d'exception</span><span class="sxs-lookup"><span data-stu-id="841e3-107">To handle an exception by using the exception message box</span></span>  
  
1.  <span data-ttu-id="841e3-108">Ajoutez une référence dans votre projet de code managé à l'assembly Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="841e3-108">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="841e3-109">Facultatif Ajoutez une `using` directive (C#) ou `Imports` ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .net) pour utiliser l' <xref:Microsoft.SqlServer.MessageBox> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="841e3-109">(Optional) Add a `using` (C#) or `Imports` ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="841e3-110">Créez un bloc try-catch pour gérer l'exception anticipée.</span><span class="sxs-lookup"><span data-stu-id="841e3-110">Create a try-catch block to handle the anticipated exception.</span></span>  
  
4.  <span data-ttu-id="841e3-111">Au sein du bloc `catch`, créez une instance de la classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="841e3-111">Within the `catch` block, create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="841e3-112">Passe l' <xref:System.Exception> objet géré par le `try` - `catch` bloc.</span><span class="sxs-lookup"><span data-stu-id="841e3-112">Pass the <xref:System.Exception> object handled by the `try`-`catch` block.</span></span>  
  
5.  <span data-ttu-id="841e3-113">(Facultatif) Définissez une ou plusieurs des propriétés suivantes sur <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> :</span><span class="sxs-lookup"><span data-stu-id="841e3-113">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="841e3-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>énumération qui spécifie les boutons à afficher dans la boîte de message d’exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="841e3-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>énumération qui spécifie le bouton par défaut pour la boîte de message d’exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the exception message box.</span></span>  
  
    -   <span data-ttu-id="841e3-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>énumération que vous utilisez pour contrôler d’autres comportements de la boîte de message d’exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="841e3-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>énumération qui spécifie le symbole à afficher dans la boîte de message d’exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
6.  <span data-ttu-id="841e3-118">Appelez la méthode <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="841e3-118">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="841e3-119">Passez la fenêtre parente à laquelle la boîte de message d'exception appartient.</span><span class="sxs-lookup"><span data-stu-id="841e3-119">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="841e3-120">Facultatif Notez la valeur de l' <xref:System.Windows.Forms.DialogResult> énumération retournée si vous devez déterminer sur quel bouton l’utilisateur a cliqué.</span><span class="sxs-lookup"><span data-stu-id="841e3-120">(Optional) Note the value of returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-without-an-exception"></a><span data-ttu-id="841e3-121">Pour afficher la boîte de message d'exception sans exception</span><span class="sxs-lookup"><span data-stu-id="841e3-121">To display the exception message box without an exception</span></span>  
  
1.  <span data-ttu-id="841e3-122">Ajoutez une référence dans votre projet de code managé à l'assembly Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="841e3-122">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="841e3-123">Facultatif Ajoutez une `using` directive (C#) ou `Imports` (Visual Basic .net) pour utiliser l' <xref:Microsoft.SqlServer.MessageBox> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="841e3-123">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="841e3-124">Créez une instance de la classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="841e3-124">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="841e3-125">Passez le texte du message comme une valeur <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="841e3-125">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="841e3-126">(Facultatif) Définissez une ou plusieurs des propriétés suivantes sur <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> :</span><span class="sxs-lookup"><span data-stu-id="841e3-126">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="841e3-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>énumération qui spécifie les boutons à afficher dans la boîte de message d’exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="841e3-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A> - légende de boîte de dialogue de la boîte de message d'exception ;</span><span class="sxs-lookup"><span data-stu-id="841e3-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A> - Dialog box caption of the exception message box.</span></span>  
  
    -   <span data-ttu-id="841e3-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>énumération qui spécifie le bouton par défaut de la boîte de dialogue de la boîte de message d’exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the dialog box of the exception message box.</span></span>  
  
    -   <span data-ttu-id="841e3-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>énumération que vous utilisez pour contrôler d’autres comportements de la boîte de message d’exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="841e3-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>énumération qui spécifie le symbole à afficher dans la boîte de message d’exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
5.  <span data-ttu-id="841e3-132">Appelez la méthode <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="841e3-132">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="841e3-133">Passez la fenêtre parente à laquelle la boîte de message d'exception appartient.</span><span class="sxs-lookup"><span data-stu-id="841e3-133">Pass the parent window to which the exception message box belongs.</span></span>  
  
6.  <span data-ttu-id="841e3-134">(Facultatif) Notez la valeur de l'énumération <xref:System.Windows.Forms.DialogResult> retournée si vous devez déterminer sur quel bouton l'utilisateur a cliqué.</span><span class="sxs-lookup"><span data-stu-id="841e3-134">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-with-customized-buttons"></a><span data-ttu-id="841e3-135">Pour afficher la boîte de message d'exception avec des boutons personnalisés</span><span class="sxs-lookup"><span data-stu-id="841e3-135">To display the exception message box with customized buttons</span></span>  
  
1.  <span data-ttu-id="841e3-136">Ajoutez une référence dans votre projet de code managé à l'assembly Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="841e3-136">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="841e3-137">Facultatif Ajoutez une `using` directive (C#) ou `Imports` (Visual Basic .net) pour utiliser l' <xref:Microsoft.SqlServer.MessageBox> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="841e3-137">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="841e3-138">Créez une instance de la classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> en appliquant l'une des deux méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="841e3-138">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="841e3-139">Passe l' <xref:System.Exception> objet géré par un `try` - `catch` bloc.</span><span class="sxs-lookup"><span data-stu-id="841e3-139">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="841e3-140">Passez le texte du message comme une valeur <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="841e3-140">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="841e3-141">Définissez l'une des valeurs suivantes pour <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> :</span><span class="sxs-lookup"><span data-stu-id="841e3-141">Set one of the following values for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>:</span></span>  
  
    -   <span data-ttu-id="841e3-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore>-affiche les boutons **abandonner**, **Réessayer**et **Ignorer** .</span><span class="sxs-lookup"><span data-stu-id="841e3-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore> - displays the **Abort**, **Retry**, and **Ignore** buttons.</span></span>  
  
    -   <span data-ttu-id="841e3-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom> - affiche les boutons personnalisés.</span><span class="sxs-lookup"><span data-stu-id="841e3-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom> - displays custom buttons.</span></span>  
  
    -   <span data-ttu-id="841e3-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK>-affiche le bouton **OK** .</span><span class="sxs-lookup"><span data-stu-id="841e3-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK> - displays the **OK** button.</span></span>  
  
    -   <span data-ttu-id="841e3-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel>-affiche les boutons **OK** et **Annuler** .</span><span class="sxs-lookup"><span data-stu-id="841e3-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel> - displays the **OK** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="841e3-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel>-affiche les boutons **Réessayer** et **Annuler** .</span><span class="sxs-lookup"><span data-stu-id="841e3-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel> - displays the **Retry** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="841e3-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo>-affiche les boutons **Oui** et **non** .</span><span class="sxs-lookup"><span data-stu-id="841e3-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo> - displays **Yes** and **No** buttons.</span></span>  
  
    -   <span data-ttu-id="841e3-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel>-affiche les boutons **Oui**, **non**et **Annuler** .</span><span class="sxs-lookup"><span data-stu-id="841e3-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel> - displays **Yes**, **No**, and **Cancel** buttons.</span></span>  
  
5.  <span data-ttu-id="841e3-149">(Facultatif) Si vous utilisez des boutons personnalisés, appelez l'une des surcharges de la méthode <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> pour spécifier le texte de cinq boutons personnalisés au plus.</span><span class="sxs-lookup"><span data-stu-id="841e3-149">(Optional) If you use custom buttons, call one of the overloads of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> method to specify text for up to five custom buttons.</span></span>  
  
6.  <span data-ttu-id="841e3-150">Appelez la méthode <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="841e3-150">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="841e3-151">Passez la fenêtre parente à laquelle la boîte de message d'exception appartient.</span><span class="sxs-lookup"><span data-stu-id="841e3-151">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="841e3-152">(Facultatif) Notez la valeur de l'énumération <xref:System.Windows.Forms.DialogResult> retournée si vous devez déterminer sur quel bouton l'utilisateur a cliqué.</span><span class="sxs-lookup"><span data-stu-id="841e3-152">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span> <span data-ttu-id="841e3-153">Si vous utilisez des boutons personnalisés, notez la valeur de <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> pour la propriété <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> pour déterminer sur lequel des boutons personnalisés l'utilisateur a cliqué.</span><span class="sxs-lookup"><span data-stu-id="841e3-153">If you use custom buttons, note the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> for the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> property to determine which of the custom buttons the user clicked.</span></span>  
  
#### <a name="to-allow-users-to-decide-whether-to-show-the-exception-message-box"></a><span data-ttu-id="841e3-154">Pour permettre aux utilisateurs de décider d'afficher ou non la boîte de message d'exception</span><span class="sxs-lookup"><span data-stu-id="841e3-154">To allow users to decide whether to show the exception message box</span></span>  
  
1.  <span data-ttu-id="841e3-155">Ajoutez une référence dans votre projet de code managé à l'assembly Microsoft.ExceptionMessageBox.dll.</span><span class="sxs-lookup"><span data-stu-id="841e3-155">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="841e3-156">Facultatif Ajoutez une `using` directive (C#) ou `Imports` (Visual Basic .net) pour utiliser l' <xref:Microsoft.SqlServer.MessageBox> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="841e3-156">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="841e3-157">Créez une instance de la classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> en appliquant l'une des deux méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="841e3-157">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="841e3-158">Passe l' <xref:System.Exception> objet géré par un `try` - `catch` bloc.</span><span class="sxs-lookup"><span data-stu-id="841e3-158">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="841e3-159">Passez le texte du message comme une valeur <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="841e3-159">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="841e3-160">Affectez à la propriété <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> la valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="841e3-160">Set the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="841e3-161">(Facultatif) Spécifiez le texte qui demande à l'utilisateur de décider d'afficher encore ou non la boîte de message d'exception pour <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span><span class="sxs-lookup"><span data-stu-id="841e3-161">(Optional) Specify the text that asks the user to decide whether to show the exception message box again for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span></span> <span data-ttu-id="841e3-162">Le texte par défaut est "Ne plus afficher ce message".</span><span class="sxs-lookup"><span data-stu-id="841e3-162">The default text is "Do not show this message again."</span></span>  
  
6.  <span data-ttu-id="841e3-163">Si vous devez conserver la décision de l'utilisateur uniquement pour la durée de l'exécution de l'application, définissez la valeur de <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> sur une variable <xref:System.Boolean> globale.</span><span class="sxs-lookup"><span data-stu-id="841e3-163">If you need to keep the user's decision only for the duration of the application's execution, set the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> to a global <xref:System.Boolean> variable.</span></span> <span data-ttu-id="841e3-164">Évaluez cette valeur avant de créer une instance de la boîte de message d'exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-164">Evaluate this value before creating an instance of the exception message box.</span></span>  
  
7.  <span data-ttu-id="841e3-165">Si vous devez stocker définitivement la décision d'un utilisateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="841e3-165">If you need to store a user's decision permanently, do the following:</span></span>  
  
    1.  <span data-ttu-id="841e3-166">Appelez la méthode CreateSubKey pour ouvrir une clé de Registre personnalisée que votre application utilise et définissez <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> sur l'objet RegistryKey retourné.</span><span class="sxs-lookup"><span data-stu-id="841e3-166">Call the CreateSubKey method to open a custom registry key that your application uses, and set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> to the returned RegistryKey object.</span></span>  
  
    2.  <span data-ttu-id="841e3-167">Attribuez à <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> le nom de la valeur de Registre utilisée.</span><span class="sxs-lookup"><span data-stu-id="841e3-167">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> to the name of the registry value that is used.</span></span>  
  
    3.  <span data-ttu-id="841e3-168">Définissez <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> sur `true`.</span><span class="sxs-lookup"><span data-stu-id="841e3-168">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> to `true`.</span></span>  
  
    4.  <span data-ttu-id="841e3-169">Appelez la méthode <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="841e3-169">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="841e3-170">La clé de Registre spécifiée est évaluée et la boîte de message d'exception est affichée uniquement si les données stockées dans la clé de Registre sont définies sur 0.</span><span class="sxs-lookup"><span data-stu-id="841e3-170">The specified registry key is evaluated, and the exception message box is displayed only if the data stored in the registry key is 0.</span></span> <span data-ttu-id="841e3-171">Si la boîte de dialogue est affichée et que l'utilisateur active la case à cocher avant de cliquer sur un bouton, les données dans la clé de Registre sont définies sur 1.</span><span class="sxs-lookup"><span data-stu-id="841e3-171">If the dialog box is displayed and the user selects the check box before clicking a button, the data in the registry key is set to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="841e3-172">Exemple</span><span class="sxs-lookup"><span data-stu-id="841e3-172">Example</span></span>  
 <span data-ttu-id="841e3-173">Cet exemple utilise la boîte de message d’exception avec le bouton **OK** uniquement pour afficher les informations d’une exception d’application qui comprend l’exception gérée ainsi que des informations supplémentaires spécifiques à l’application.</span><span class="sxs-lookup"><span data-stu-id="841e3-173">This example uses the exception message box with only the **OK** button to display information from an application exception that includes the handled exception along with additional application-specific information.</span></span>  
  
 [!code-csharp[HowTo#emb_showOKbutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showokbutton)]  
  
 [!code-vb[HowTo#emb_vb_showOKbutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showokbutton)]  
  
## <a name="example"></a><span data-ttu-id="841e3-174">Exemple</span><span class="sxs-lookup"><span data-stu-id="841e3-174">Example</span></span>  
 <span data-ttu-id="841e3-175">Cet exemple utilise la boîte de message d’exception avec les boutons **Oui** et **non** que l’utilisateur choisit.</span><span class="sxs-lookup"><span data-stu-id="841e3-175">This example uses the exception message box with **Yes** and **No** buttons from which the user chooses.</span></span>  
  
 [!code-csharp[HowTo#emb_showYesNobutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showyesnobutton)]  
  
 [!code-vb[HowTo#emb_vb_showYesNobutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showyesnobutton)]  
  
## <a name="example"></a><span data-ttu-id="841e3-176">Exemple</span><span class="sxs-lookup"><span data-stu-id="841e3-176">Example</span></span>  
 <span data-ttu-id="841e3-177">Cet exemple utilise la boîte de message d'exception avec des boutons personnalisés.</span><span class="sxs-lookup"><span data-stu-id="841e3-177">This example uses the exception message box with custom buttons.</span></span>  
  
 [!code-csharp[HowTo#emb_showcustombutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showcustombutton)]  
  
 [!code-vb[HowTo#emb_vb_showcustombutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showcustombutton)]  
  
## <a name="example"></a><span data-ttu-id="841e3-178">Exemple</span><span class="sxs-lookup"><span data-stu-id="841e3-178">Example</span></span>  
 <span data-ttu-id="841e3-179">Cet exemple utilise la case à cocher pour déterminer s'il faut afficher la boîte de message d'exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-179">This example uses the check box to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_usecheckbox](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_usecheckbox)]  
  
 [!code-vb[HowTo#emb_vb_usecheckbox](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_usecheckbox)]  
  
## <a name="example"></a><span data-ttu-id="841e3-180">Exemple</span><span class="sxs-lookup"><span data-stu-id="841e3-180">Example</span></span>  
 <span data-ttu-id="841e3-181">Cet exemple utilise la case à cocher et une clé du Registre pour déterminer s'il faut afficher la boîte de message d'exception.</span><span class="sxs-lookup"><span data-stu-id="841e3-181">This example uses the check box and a registry key to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_useregkey](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_useregkey)]  
  
 [!code-vb[HowTo#emb_vb_useregkey](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_useregkey)]  
  
## <a name="example"></a><span data-ttu-id="841e3-182">Exemple</span><span class="sxs-lookup"><span data-stu-id="841e3-182">Example</span></span>  
 <span data-ttu-id="841e3-183">Cet exemple utilise la boîte de message d'exception pour afficher des informations supplémentaires utiles lors d'un dépannage ou d'un débogage.</span><span class="sxs-lookup"><span data-stu-id="841e3-183">This example uses the exception message box to show additional information that is helpful when troubleshooting or debugging.</span></span>  
  
 [!code-csharp[HowTo#emb_moreinfo](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_moreinfo)]  
  
 [!code-vb[HowTo#emb_vb_moreinfo](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_moreinfo)]  
  
  
