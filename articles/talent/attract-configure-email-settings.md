---
title: Skonfiguruj ustawienia wiadomości e-mail w Microsoft Dynamics 365 for Talent - Attract
description: W tym temacie wyjaśniono, jak skonfigurować ustawienia wiadomości e-mail wysyłanych przez Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: a8cf59064dd2f66ee50a0b0566aa712ba1f72dea
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739502"
---
# <a name="configure-email-settings"></a><span data-ttu-id="d16eb-103">Konfigurowanie ustawień poczty e-mail</span><span class="sxs-lookup"><span data-stu-id="d16eb-103">Configure email settings</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d16eb-104">Twoja marka buduje zaufanie i pomaga budować relacje z kandydatami, zanim nawet zaczną starać się o stanowiska.</span><span class="sxs-lookup"><span data-stu-id="d16eb-104">Your brand establishes trust and helps you build a relationship with candidates before they even apply for your positions.</span></span> <span data-ttu-id="d16eb-105">Pozytywne postrzeganie marki przyciąga największe talenty i zwiększa lojalność obecnych pracowników.</span><span class="sxs-lookup"><span data-stu-id="d16eb-105">Positive brand perception attracts top talent and increases the loyalty of existing employees.</span></span> <span data-ttu-id="d16eb-106">Microsoft Dynamics 365 for Talent: Attract pozwala ci skonfigurować wiadomości e-mail w taki sposób, który będzie najlepiej wyraźał markę Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="d16eb-106">Microsoft Dynamics 365 for Talent: Attract lets you configure emails so that they reflect your company's brand.</span></span> <span data-ttu-id="d16eb-107">W związku z tym możesz zapewnić spójne doświadczenie kandydatom w trakcie procesu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d16eb-107">Therefore, you can provide a consistent experience to job candidates as they progress through the application process.</span></span>

<span data-ttu-id="d16eb-108">Attract pozwala wykonać następujące akcje:</span><span class="sxs-lookup"><span data-stu-id="d16eb-108">Attract lets you perform these actions:</span></span>

- <span data-ttu-id="d16eb-109">Skonfiguruj ustawienia poczty e-mail, aby korzystać z konta usługi poczty e-mail Microsoft Exchange dla Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="d16eb-109">Configure email settings so that your company's Microsoft Exchange email service account is used.</span></span> <span data-ttu-id="d16eb-110">W ten sposób kandydaci wiedzą, że wiadomości e-mail pochodzą z Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="d16eb-110">In this way, candidates know that the emails are coming from your company.</span></span> <span data-ttu-id="d16eb-111">Na przykład możesz skonfigurować ustawienia, aby kandydaci otrzymywali wiadomości e-mail od `recruiting@contoso.com` zamiast `contoso@microsoft.com`.</span><span class="sxs-lookup"><span data-stu-id="d16eb-111">For example, you can configure your settings so that candidates receive emails from `recruiting@contoso.com` instead of `contoso@microsoft.com`.</span></span>
- <span data-ttu-id="d16eb-112">Stwórz spójną markę dla wszystkich wiadomości e-mail, ustawiając globalny nagłówek i stopkę dla szablonów wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="d16eb-112">Create consistent branding for all your email communications by setting a global header and footer for email templates.</span></span> 

> [!NOTE]
> <span data-ttu-id="d16eb-113">Skonfiguruj aplikację Attract, aby korzystała z konta usługi e-mail Twojej firmy do wysyłania wiadomości e-mail, potrzebny jest kompleksowy dodatek zatrudniania.</span><span class="sxs-lookup"><span data-stu-id="d16eb-113">To configure Attract so that it uses your company's email service account to send email, you need the Comprehensive hiring add-on.</span></span>

## <a name="connect-an-email-service-account"></a><span data-ttu-id="d16eb-114">Połącz konto wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="d16eb-114">Connect an email service account</span></span>

<span data-ttu-id="d16eb-115">Poprzez połaczenie konta e-mail Twojej firmy, możesz stworzyć wyjątkowo spójne doświadczenie dla kandydatów.</span><span class="sxs-lookup"><span data-stu-id="d16eb-115">By connecting your company's email service account, you can create a branded email experience for your job candidates.</span></span> <span data-ttu-id="d16eb-116">Jeśli nie połączysz konta e-mail Twojej firmy, aplikacja Attract automatycznie używa konta z nazewnictwem Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d16eb-116">If you don't connect your company account, Attract uses the default Microsoft-branded email service account.</span></span>

1. <span data-ttu-id="d16eb-117">Wybierz **Ustawienia** (symbol koła zębatego w prawym górnym rogu), a następnie wybierz **Centrum administracji**.</span><span class="sxs-lookup"><span data-stu-id="d16eb-117">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="d16eb-118">W karcie **Ustawienia e-mail** pod **Konta e-mail** wybierz **Połącz konto firmowe**.</span><span class="sxs-lookup"><span data-stu-id="d16eb-118">On the **Email settings** tab, under **Email service accounts**, select **Connect a company account**.</span></span>

    ![Połącznienie Twojego firmowego konta e-mail w aplikacji Attract](./media/attract-admin-email-service-accounts.png)

    <span data-ttu-id="d16eb-120">Więcej informacji na temat tworzenia wspólnego konta e-mail znajdziesz: [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="d16eb-120">For more information about how to create a shared email account, see [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span></span>

3. <span data-ttu-id="d16eb-121">Zaloguj się w oknie logowania Microsoft używając firmowych danych.</span><span class="sxs-lookup"><span data-stu-id="d16eb-121">In the Microsoft sign-in window, sign in by using your corporate credentials.</span></span>
4. <span data-ttu-id="d16eb-122">Jeśli nie skonfigurowałeś jeszcze konta usługi e-mail lub chcesz dodać nowe, wybierz **Dodaj nowe konto usługi**, a następnie wprowadź dane konta e-mail.</span><span class="sxs-lookup"><span data-stu-id="d16eb-122">If you haven't yet set up an email service account, or if you want to add a new one, select **Add new service account**, and then enter your email information.</span></span> <span data-ttu-id="d16eb-123">Jeśli masz już skonfigurowane konto usługi e-mail, którego chcesz użyć, wybierz je.</span><span class="sxs-lookup"><span data-stu-id="d16eb-123">If you've already set up the email service account that you want to use, select it.</span></span>

<span data-ttu-id="d16eb-124">Po pomyślnym skonfigurowaniu konta usługi e-mail, znajdziesz je w **Konta e-mail**.</span><span class="sxs-lookup"><span data-stu-id="d16eb-124">When your email service account is successfully configured, you will see it listed under **Email service accounts**.</span></span>

## <a name="disconnect-an-email-service-account"></a><span data-ttu-id="d16eb-125">Odłącz konto wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="d16eb-125">Disconnect an email service account</span></span>

<span data-ttu-id="d16eb-126">Jeśli chcesz zaprzestać korzystania z domeny firmy w komunikacji e-mail w aplikacji Attract, możesz odłączyć konto usługi e-mail.</span><span class="sxs-lookup"><span data-stu-id="d16eb-126">If you want to stop using your company's domain in email communications through Attract, you can disconnect an email service account.</span></span>

1. <span data-ttu-id="d16eb-127">Wybierz **Ustawienia** (symbol koła zębatego w prawym górnym rogu), a następnie wybierz **Centrum administracji**.</span><span class="sxs-lookup"><span data-stu-id="d16eb-127">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="d16eb-128">W karcie **Ustawienia e-mail** pod **Konta e-mail** wybierz przycisk **Więcej** (trzy pionowe kropki) obok konta usługi e-mail, które chcesz rozłączyć.</span><span class="sxs-lookup"><span data-stu-id="d16eb-128">On the **Email settings** tab, under **Email service accounts**, select the **More** button (three vertical dots) next to the email service account that you want to disconnect.</span></span>
3. <span data-ttu-id="d16eb-129">Wybierz **Odłącz konto e-mail**</span><span class="sxs-lookup"><span data-stu-id="d16eb-129">Select **Disconnect email account**.</span></span>

    ![Odłączanie firmowego konta e-mail](./media/attract-admin-disconnect-email-account.png)

4. <span data-ttu-id="d16eb-131">Gdy pojawi się prośba o potwierdzenie operacji, wybierz **Odłącz**.</span><span class="sxs-lookup"><span data-stu-id="d16eb-131">When you're prompted to confirm the operation, select **Disconnect**.</span></span>

    ![Potwierdzenie odłączenia firmowego konta e-mail](./media/attract-admin-email-confirm-disconnect.png)

<span data-ttu-id="d16eb-133">Jeśli nie połączysz innego konta e-mail, aplikacja Attract automatycznie używa konta z nazewnictwem Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d16eb-133">If you don't connect a different email service account, emails that are sent from Attract will use the default Microsoft-branded email service account.</span></span>

## <a name="configure-email-template-settings"></a><span data-ttu-id="d16eb-134">Skonfiguruj ustawienia szablonów e-mail</span><span class="sxs-lookup"><span data-stu-id="d16eb-134">Configure email template settings</span></span>

<span data-ttu-id="d16eb-135">Możesz przesłać obraz logo swojej firmy i inne informacje w postaci nagłówka oznaczonego marką dla wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="d16eb-135">You can upload an image of your company's logo and other information as a branded header for your emails.</span></span> <span data-ttu-id="d16eb-136">Możesz również podać linki do swojej polityki prywatności i warunków korzystania w stopkach wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="d16eb-136">You can also provide links to your privacy policy and terms of use in email footers.</span></span>

> [!NOTE]
> <span data-ttu-id="d16eb-137">Musisz przestrzegać wszystkich obowiązujących przepisów prawa w Twoim kraju lub regionie, a także kraju lub regionu odbiorcy wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="d16eb-137">You must comply with all applicable laws of your country or region, and also the country or region that governs the email recipient.</span></span> <span data-ttu-id="d16eb-138">Przepisy te obejmują przepisy antyspamowe.</span><span class="sxs-lookup"><span data-stu-id="d16eb-138">These laws include anti-spam regulations.</span></span>

1. <span data-ttu-id="d16eb-139">Wybierz **Ustawienia** (symbol koła zębatego w prawym górnym rogu), a następnie wybierz **Centrum administracji**.</span><span class="sxs-lookup"><span data-stu-id="d16eb-139">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="d16eb-140">Na karcie **Ustawienia e-mail** pod **Ustawienia szablonów wiadomości e-mail**, przeciągnij obraz, którego chcesz użyć jako nagłówka wiadomości e-mail, do pola obrazu lub kliknij pole obrazu, aby wyszukać plik.</span><span class="sxs-lookup"><span data-stu-id="d16eb-140">On the **Email settings** tab, under **Email template settings**, drag the image that you want to use as your email header into the image box, or click in the image box to browse for the file.</span></span> <span data-ttu-id="d16eb-141">Aby zastąpić istniejący obraz, musisz najpierw wybrać opcję **Usuń** obok niego.</span><span class="sxs-lookup"><span data-stu-id="d16eb-141">To replace an existing image, you must first select **Remove** next to it.</span></span> <span data-ttu-id="d16eb-142">Obraz musi być w formacie JPEG, JPG, PNG, lub SVG.</span><span class="sxs-lookup"><span data-stu-id="d16eb-142">The image must be a JPEG, JPG, PNG, or SVG file.</span></span> <span data-ttu-id="d16eb-143">Zalecany rozmiar dla obrazów wynosi od 25 do 800 pikseli szerokości i od 25 do 150 pikseli wysokości.</span><span class="sxs-lookup"><span data-stu-id="d16eb-143">The recommended size for images is between 25 and 800 pixels wide, and between 25 and 150 pixels high.</span></span> <span data-ttu-id="d16eb-144">Maksymalny rozmiar pliku nagłówka wynosi 1 megabajt (MB).</span><span class="sxs-lookup"><span data-stu-id="d16eb-144">The maximum file size for the header is 1 megabyte (MB).</span></span>

    ![Dodawanie obrazu do nagłówka wiadomości e-mail Twojej firmy](./media/attract-admin-email-header.png)

3. <span data-ttu-id="d16eb-146">Pod adresem **Twoja polityka prywatności dotycząca komunikacji** podaj link do polityki prywatności firmy.</span><span class="sxs-lookup"><span data-stu-id="d16eb-146">Under **Your Privacy policy for communications**, provide a link to your company's privacy policy.</span></span> <span data-ttu-id="d16eb-147">Pod adresem **Twoje zasady i warunki dotyczące komunikacji** podaj link do zasad i warunków firmy.</span><span class="sxs-lookup"><span data-stu-id="d16eb-147">Under **Your Terms and conditions for communication**, provide a link to your company's terms of use.</span></span>

    ![Dodawanie linków do polityki prywatności i warunków korzystania firmy w stopkach wiadomości e-mail.](./media/attract-admin-email-footer.png)

4. <span data-ttu-id="d16eb-149">Wybierz **Zapisz**, żeby zapisać ustawienia szablonu e-mail.</span><span class="sxs-lookup"><span data-stu-id="d16eb-149">Select **Save** to save your email template settings.</span></span>
