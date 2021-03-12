---
title: Konfigurowanie opcjonalnych funkcji środowiska oceny usługi Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania funkcji opcjonalnych środowiska oceny Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6639de250557ce9a25fc2cde3807abf64b0ddc18
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993457"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="827be-103">Konfigurowanie opcjonalnych funkcji środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="827be-103">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="827be-104">W tym temacie opisano sposób konfigurowania funkcji opcjonalnych środowiska oceny Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="827be-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="827be-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="827be-105">Prerequisites</span></span>

<span data-ttu-id="827be-106">Jeśli chcesz ocenić funkcje transakcyjnej poczty e-mail, muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="827be-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="827be-107">Jest dostępny serwer poczty e-mail (serwer Simple Mail Transfer Protocol \[SMTP\]), który może być używany z poziomu subskrypcji platformy Microsoft Azure, w której jest inicjowane środowisko oceny.</span><span class="sxs-lookup"><span data-stu-id="827be-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the evaluation environment.</span></span>
- <span data-ttu-id="827be-108">Masz dostęp do w pełni kwalifikowanej nazwy (FQDN)/adresu IP serwera, numeru portu SMTP oraz szczegółów uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="827be-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="827be-109">Konfigurowanie zaplecza obrazu</span><span class="sxs-lookup"><span data-stu-id="827be-109">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="827be-110">Znajdowanie podstawowego adresu URL multimediów</span><span class="sxs-lookup"><span data-stu-id="827be-110">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="827be-111">Aby można było wykonać tę procedurę, należy wykonać kroki opisane w części [Konfigurowanie witryny w usłudze Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="827be-111">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="827be-112">Zaloguj się do konstruktora witryny Commerce przy użyciu adresu URL zanotowanego podczas inicjowania usługi handlu elektronicznego w trakcie aprowizacji (zobacz [Inicjowanie usługi handlu elektronicznego](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="827be-112">Sign in to the Commerce site builder by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="827be-113">Otwórz witrynę **Fabrikam** .</span><span class="sxs-lookup"><span data-stu-id="827be-113">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="827be-114">W menu po lewej stronie wybierz pozycję **Biblioteka multimediów**.</span><span class="sxs-lookup"><span data-stu-id="827be-114">On the menu on the left, select **Media Library**.</span></span>
1. <span data-ttu-id="827be-115">Wybierz dowolny składnik majątku dla pojedynczego obrazu.</span><span class="sxs-lookup"><span data-stu-id="827be-115">Select any single image asset.</span></span>
1. <span data-ttu-id="827be-116">W inspektorze właściwości po prawej stronie znajdź właściwość **Publiczny adres URL**.</span><span class="sxs-lookup"><span data-stu-id="827be-116">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="827be-117">Wartość to adres URL.</span><span class="sxs-lookup"><span data-stu-id="827be-117">The value is a URL.</span></span> <span data-ttu-id="827be-118">Oto przykład:</span><span class="sxs-lookup"><span data-stu-id="827be-118">Here is an example:</span></span>

    <span data-ttu-id="827be-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="827be-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="827be-120">Zastąp ostatni identyfikator w adresie URL (**MA1nQC** w poprzednim przykładzie) następującym ciągiem: **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="827be-120">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="827be-121">Oto przykładowy adres URL po wprowadzeniu tej zmiany:</span><span class="sxs-lookup"><span data-stu-id="827be-121">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="827be-122">Ten adres URL jest podstawowym adresem URL obiektu multimedialnego.</span><span class="sxs-lookup"><span data-stu-id="827be-122">This URL is your media base URL.</span></span> <span data-ttu-id="827be-123">Zanotuj go.</span><span class="sxs-lookup"><span data-stu-id="827be-123">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="827be-124">Aktualizowanie podstawowego adresu URL obiektu multimedialnego</span><span class="sxs-lookup"><span data-stu-id="827be-124">Update the media base URL</span></span>

1. <span data-ttu-id="827be-125">Zaloguj się do Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="827be-125">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="827be-126">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail i Commerce \> Ustawienia kanału \> Profile kanału**.</span><span class="sxs-lookup"><span data-stu-id="827be-126">Use the menu on the left to go to **Modules \> Retail and commerce \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="827be-127">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="827be-127">Select **Edit**.</span></span>
1. <span data-ttu-id="827be-128">W obszarze **Właściwości profilu** zastąp wartość właściwości **Podstawowy adres URL serwera multimediów** utworzonym wcześniej podstawowym adresem URL obiektu multimedialnego.</span><span class="sxs-lookup"><span data-stu-id="827be-128">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="827be-129">Wybierz kanał o nazwie **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="827be-129">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="827be-130">W obszarze **Właściwości profilu** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="827be-130">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="827be-131">Dla dodanej właściwości wybierz pozycję **Podstawowy adres URL serwera multimediów** jako klucz właściwości.</span><span class="sxs-lookup"><span data-stu-id="827be-131">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="827be-132">Jako wartość właściwości wprowadź podstawowy adres URL obiektu multimedialnego, który został utworzony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="827be-132">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="827be-133">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="827be-133">Select **Save**.</span></span>

## <a name="configure-and-test-the-email-server"></a><span data-ttu-id="827be-134">Konfigurowanie i testowanie serwera poczty e-mail</span><span class="sxs-lookup"><span data-stu-id="827be-134">Configure and test the email server</span></span>

> [!NOTE]
> <span data-ttu-id="827be-135">Wprowadzony tutaj serwer SMTP lub usługa poczty e-mail musi być dostępna z poziomu subskrypcji platformy Azure używanej dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="827be-135">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="827be-136">Zaloguj się do Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="827be-136">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="827be-137">Korzystając z menu po lewej stronie, przejdź do **Moduły \> Retail and Commerce \> Ustawienia centrali \> Parametry \> Parametry poczty e-mail**.</span><span class="sxs-lookup"><span data-stu-id="827be-137">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Email parameters**.</span></span>
1. <span data-ttu-id="827be-138">Na karcie **Ustawienia SMTP** w polu **Serwer poczty wychodzącej** wprowadź nazwę FQDN lub adres IP serwera SMTP lub usługi poczty e-mail.</span><span class="sxs-lookup"><span data-stu-id="827be-138">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="827be-139">W polu **Numer portu SMTP** wprowadź numer portu.</span><span class="sxs-lookup"><span data-stu-id="827be-139">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="827be-140">(Jeśli nie korzystasz z protokołu Secure Sockets Layer \[SSL\] domyślnym numerem portu jest **25**).</span><span class="sxs-lookup"><span data-stu-id="827be-140">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="827be-141">Jeśli wymagane jest uwierzytelnianie, wprowadź wartości w polach **Nazwa użytkownika** i **Hasło**.</span><span class="sxs-lookup"><span data-stu-id="827be-141">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="827be-142">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="827be-142">Select **Save**.</span></span>
1. <span data-ttu-id="827be-143">Wybierz pozycję **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="827be-143">Select **Refresh**.</span></span>
1. <span data-ttu-id="827be-144">Na karcie **Testowa wiadomość e-mail** w polu **Dostawca poczty e-mail** wybierz pozycję **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="827be-144">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="827be-145">W polu **Wyślij do** wprowadź adres e-mail, pod który powinna zostać dostarczona testowa wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="827be-145">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="827be-146">Wybierz pozycję **Wyślij testową wiadomość e-mail**.</span><span class="sxs-lookup"><span data-stu-id="827be-146">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="827be-147">Konfigurowanie szablonów poczty e-mail</span><span class="sxs-lookup"><span data-stu-id="827be-147">Configure email templates</span></span>

<span data-ttu-id="827be-148">Dla każdego zdarzenia transakcyjnego, w ramach którego chcesz wysyłać wiadomości e-mail, musisz zaktualizować szablon wiadomości e-mail za pomocą prawidłowego adresu e-mail nadawcy.</span><span class="sxs-lookup"><span data-stu-id="827be-148">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="827be-149">Zaloguj się do Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="827be-149">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="827be-150">Korzystając z menu po lewej stronie, przejdź do **Moduły \> Retail and Commerce \> Ustawienia centrali \> Parametry \> Szablony wiadomości e-mail organizacji**.</span><span class="sxs-lookup"><span data-stu-id="827be-150">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="827be-151">Wybierz **Pokaż listę**.</span><span class="sxs-lookup"><span data-stu-id="827be-151">Select **Show list**.</span></span>
1. <span data-ttu-id="827be-152">Dla każdego szablonu na liście należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="827be-152">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="827be-153">W polu **Adres e-mail nadawcy** wprowadź adres e-mail dla nadawcy.</span><span class="sxs-lookup"><span data-stu-id="827be-153">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="827be-154">Opcjonalnie: w polu **Nazwa nadawcy** wprowadź nazwę, która ma być używana jako nazwa nadawcy.</span><span class="sxs-lookup"><span data-stu-id="827be-154">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="827be-155">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="827be-155">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="827be-156">Dostosowywanie szablonów wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="827be-156">Customize email templates</span></span>

<span data-ttu-id="827be-157">Możesz dostosować szablony wiadomości e-mail, tak aby były używane różne obrazy.</span><span class="sxs-lookup"><span data-stu-id="827be-157">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="827be-158">Możesz również zaktualizować linki w szablonach, tak aby przenosiły Cię do środowiska oceny.</span><span class="sxs-lookup"><span data-stu-id="827be-158">Or you might want to update the links in the templates so that they go to your evaluation environment.</span></span> <span data-ttu-id="827be-159">W poniższej procedurze opisano sposób pobierania szablonów domyślnych, dostosowywania ich i aktualizowania szablonów w systemie.</span><span class="sxs-lookup"><span data-stu-id="827be-159">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="827be-160">W przeglądarce internetowej pobierz [plik zip domyślnych szablonów wiadomości e-mail oceny aplikacji Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) na komputer lokalny.</span><span class="sxs-lookup"><span data-stu-id="827be-160">In a web browser, download the [Microsoft Dynamics 365 Commerce Evaluation default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="827be-161">Ten plik zawiera następujące dokumenty HTML:</span><span class="sxs-lookup"><span data-stu-id="827be-161">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="827be-162">Szablon potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="827be-162">Order confirmation template</span></span>
    - <span data-ttu-id="827be-163">Wystaw szablon karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="827be-163">Issue gift card template</span></span>
    - <span data-ttu-id="827be-164">Szablon nowego zamówienia</span><span class="sxs-lookup"><span data-stu-id="827be-164">New order template</span></span>
    - <span data-ttu-id="827be-165">Zapakuj szablon zamówienia</span><span class="sxs-lookup"><span data-stu-id="827be-165">Pack order template</span></span>
    - <span data-ttu-id="827be-166">Wybierz szablon zamówienia</span><span class="sxs-lookup"><span data-stu-id="827be-166">Pick order template</span></span>

1. <span data-ttu-id="827be-167">Szablony dostosowuje się za pomocą edytora tekstów lub HTML.</span><span class="sxs-lookup"><span data-stu-id="827be-167">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="827be-168">Zobacz listę [obsługiwanych tokenów](#supported-tokens-in-the-email-template) w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="827be-168">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="827be-169">Zaloguj się do aplikacji Commerce.</span><span class="sxs-lookup"><span data-stu-id="827be-169">Sign in to Commerce.</span></span>
1. <span data-ttu-id="827be-170">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Administrowanie organizacją \> Ustawienia \> Szablony wiadomości e-mail organizacji**.</span><span class="sxs-lookup"><span data-stu-id="827be-170">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="827be-171">Aby wyświetlić wszystkie szablony, należy rozwinąć listę po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="827be-171">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="827be-172">Dla każdego szablonu, który chcesz dostosować, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="827be-172">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="827be-173">Wybierz szablon ma liście.</span><span class="sxs-lookup"><span data-stu-id="827be-173">Select the template in the list.</span></span>
    1. <span data-ttu-id="827be-174">W obszarze **Zawartość wiadomości e-mail** wybierz odpowiednią wersję językową na liście.</span><span class="sxs-lookup"><span data-stu-id="827be-174">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="827be-175">(Domyślny język to **en-us**).</span><span class="sxs-lookup"><span data-stu-id="827be-175">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="827be-176">W obszarze **Zawartość wiadomości e-mail** wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="827be-176">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="827be-177">Zostanie wyświetlone okienko **Przekaż szablon wiadomości e-mail**.</span><span class="sxs-lookup"><span data-stu-id="827be-177">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="827be-178">Wybierz pozycję **Przeglądaj** i znajdź plik HTML, który ma dostosowaną zawartość.</span><span class="sxs-lookup"><span data-stu-id="827be-178">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="827be-179">Wybierz pozycję **Przekaż**.</span><span class="sxs-lookup"><span data-stu-id="827be-179">Select **Upload**.</span></span> <span data-ttu-id="827be-180">Szablon zostanie przekazany do systemu i zostanie wyświetlony podgląd.</span><span class="sxs-lookup"><span data-stu-id="827be-180">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="827be-181">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="827be-181">Select **OK**.</span></span>
    1. <span data-ttu-id="827be-182">Opcjonalnie: dostosuj właściwość **Temat** szablonu.</span><span class="sxs-lookup"><span data-stu-id="827be-182">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="827be-183">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="827be-183">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="827be-184">Obsługiwane tokeny w szablonie wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="827be-184">Supported tokens in the email template</span></span>

<span data-ttu-id="827be-185">Podczas renderowania poczty e-mail te tokeny zostaną zastąpione rzeczywistymi wartościami, które dotyczą klienta i jego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="827be-185">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="827be-186">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="827be-186">Sales order</span></span>

<span data-ttu-id="827be-187">Poniższe tokeny mają zastosowanie do całego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="827be-187">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="827be-188">Nazwa tokena</span><span class="sxs-lookup"><span data-stu-id="827be-188">Name of the token</span></span> | <span data-ttu-id="827be-189">Token </span><span class="sxs-lookup"><span data-stu-id="827be-189">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="827be-190">Numer zamówienia</span><span class="sxs-lookup"><span data-stu-id="827be-190">Order number</span></span>      | <span data-ttu-id="827be-191">%salesid%</span><span class="sxs-lookup"><span data-stu-id="827be-191">%salesid%</span></span> |
| <span data-ttu-id="827be-192">Nazwa odbiorcy</span><span class="sxs-lookup"><span data-stu-id="827be-192">Customer's name</span></span>   | <span data-ttu-id="827be-193">%customername%</span><span class="sxs-lookup"><span data-stu-id="827be-193">%customername%</span></span> |
| <span data-ttu-id="827be-194">Adres dostawy</span><span class="sxs-lookup"><span data-stu-id="827be-194">Delivery address</span></span>  | <span data-ttu-id="827be-195">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="827be-195">%deliveryaddress%</span></span> |
| <span data-ttu-id="827be-196">Adres do faktury</span><span class="sxs-lookup"><span data-stu-id="827be-196">Billing address</span></span>   | <span data-ttu-id="827be-197">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="827be-197">%customeraddress%</span></span> |
| <span data-ttu-id="827be-198">Data zamówienia</span><span class="sxs-lookup"><span data-stu-id="827be-198">Order date</span></span>        | <span data-ttu-id="827be-199">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="827be-199">%shipdate%</span></span> |
| <span data-ttu-id="827be-200">Metoda dostawy</span><span class="sxs-lookup"><span data-stu-id="827be-200">Delivery mode</span></span>     | <span data-ttu-id="827be-201">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="827be-201">%modeofdelivery%</span></span> |
| <span data-ttu-id="827be-202">Dyskonto</span><span class="sxs-lookup"><span data-stu-id="827be-202">Discount</span></span>          | <span data-ttu-id="827be-203">%discount%</span><span class="sxs-lookup"><span data-stu-id="827be-203">%discount%</span></span> |
| <span data-ttu-id="827be-204">Podatek</span><span class="sxs-lookup"><span data-stu-id="827be-204">Sales tax</span></span>         | <span data-ttu-id="827be-205">%tax%</span><span class="sxs-lookup"><span data-stu-id="827be-205">%tax%</span></span> |
| <span data-ttu-id="827be-206">Suma zamówienia</span><span class="sxs-lookup"><span data-stu-id="827be-206">Order total</span></span>       | <span data-ttu-id="827be-207">%total%</span><span class="sxs-lookup"><span data-stu-id="827be-207">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="827be-208">Wiersz sprzedaży</span><span class="sxs-lookup"><span data-stu-id="827be-208">Sales line</span></span>

<span data-ttu-id="827be-209">Dla każdego produktu w zamówieniu następujące tokeny są wypełniane wartościami.</span><span class="sxs-lookup"><span data-stu-id="827be-209">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="827be-210">Umieść token **Lista produktów — początek** na początku bloku kodu HTML, który jest powtarzany dla każdego produktu, a token **Lista produktów — koniec** na końcu bloku.</span><span class="sxs-lookup"><span data-stu-id="827be-210">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="827be-211">Nazwa tokena</span><span class="sxs-lookup"><span data-stu-id="827be-211">Name of the token</span></span>      | <span data-ttu-id="827be-212">Token</span><span class="sxs-lookup"><span data-stu-id="827be-212">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="827be-213">Lista produktów - start</span><span class="sxs-lookup"><span data-stu-id="827be-213">Product list - start</span></span>   | \<!--%tablebegin.salesline% --\> |
| <span data-ttu-id="827be-214">Lista produktów - koniec</span><span class="sxs-lookup"><span data-stu-id="827be-214">Product list - end</span></span>     | \<!--%tableend.salesline%--\> |
| <span data-ttu-id="827be-215">Nazwa produktu</span><span class="sxs-lookup"><span data-stu-id="827be-215">Product name</span></span>           | <span data-ttu-id="827be-216">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="827be-216">%lineproductname%</span></span> |
| <span data-ttu-id="827be-217">opis</span><span class="sxs-lookup"><span data-stu-id="827be-217">Description</span></span>            | <span data-ttu-id="827be-218">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="827be-218">%lineproductdescription%</span></span> |
| <span data-ttu-id="827be-219">Ilość</span><span class="sxs-lookup"><span data-stu-id="827be-219">Quantity</span></span>               | <span data-ttu-id="827be-220">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="827be-220">%linequantity%</span></span> |
| <span data-ttu-id="827be-221">Cena wiersza jednostki</span><span class="sxs-lookup"><span data-stu-id="827be-221">Line unit price</span></span>        | <span data-ttu-id="827be-222">%lineprice% (sprawdź)</span><span class="sxs-lookup"><span data-stu-id="827be-222">%lineprice% (verify)</span></span> |
| <span data-ttu-id="827be-223">Wszystkie pozycje w wierszu</span><span class="sxs-lookup"><span data-stu-id="827be-223">line item total</span></span>        | <span data-ttu-id="827be-224">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="827be-224">%linenetamount%</span></span> |
| <span data-ttu-id="827be-225">rabat wiersza</span><span class="sxs-lookup"><span data-stu-id="827be-225">line discount</span></span>          | <span data-ttu-id="827be-226">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="827be-226">%linediscount%</span></span> |
| <span data-ttu-id="827be-227">Data wysyłki</span><span class="sxs-lookup"><span data-stu-id="827be-227">Ship date</span></span>              | <span data-ttu-id="827be-228">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="827be-228">%lineshipdate%</span></span> |
| <span data-ttu-id="827be-229">Metoda zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="827be-229">Procurement method</span></span>     | <span data-ttu-id="827be-230">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="827be-230">%linedeliverymode%</span></span> |
| <span data-ttu-id="827be-231">adres dostawy</span><span class="sxs-lookup"><span data-stu-id="827be-231">delivery address</span></span>       | <span data-ttu-id="827be-232">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="827be-232">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="827be-233">Jednostka sprzedaży dla wiersza</span><span class="sxs-lookup"><span data-stu-id="827be-233">Sales unit of the line</span></span> | <span data-ttu-id="827be-234">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="827be-234">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="827be-235">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="827be-235">Additional resources</span></span>

[<span data-ttu-id="827be-236">Omówienie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="827be-236">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="827be-237">Ustanowienie środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="827be-237">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="827be-238">Konfigurowanie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="827be-238">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="827be-239">Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="827be-239">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="827be-240">Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="827be-240">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="827be-241">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="827be-241">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="827be-242">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="827be-242">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="827be-243">Portal Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="827be-243">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="827be-244">Witryna Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="827be-244">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
