---
title: Konfiguruj funkcje opcjonalne środowiska wersji zapoznawczej usługi Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania funkcji opcjonalnych środowiska wersji zapoznawczej aplikacji Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4b17f8e9b0d8a9a62714d0073561e66642b2eaf9
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057747"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="030d8-103">Konfiguruj funkcje opcjonalne środowiska wersji zapoznawczej usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="030d8-103">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="030d8-104">W tym temacie opisano sposób konfigurowania funkcji opcjonalnych środowiska wersji zapoznawczej aplikacji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="030d8-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="030d8-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="030d8-105">Prerequisites</span></span>

<span data-ttu-id="030d8-106">Jeśli chcesz ocenić funkcje transakcyjnej poczty e-mail, muszą być spełnione następujące wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="030d8-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="030d8-107">Jest dostępny serwer poczty e-mail (serwer Simple Mail Transfer Protocol \[SMTP\]), który może być używany z poziomu subskrypcji platformy Microsoft Azure, w której jest inicjowane środowisko wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="030d8-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the preview environment.</span></span>
- <span data-ttu-id="030d8-108">Masz dostęp do w pełni kwalifikowanej nazwy (FQDN)/adresu IP serwera, numeru portu SMTP oraz szczegółów uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="030d8-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

<span data-ttu-id="030d8-109">Jeśli chcesz ocenić funkcje zarządzania cyfrowymi składnikami majątku przez pozyskanie nowych obrazów obsługi wielokanałowej, musisz mieć dostępną nazwę dzierżawy systemu zarządzania zawartością (CMS).</span><span class="sxs-lookup"><span data-stu-id="030d8-109">If you want to evaluate Digital Asset Management features by ingesting new omni-channel images, you must have the name of your content management system (CMS) tenant available.</span></span> <span data-ttu-id="030d8-110">Instrukcje dotyczące znajdowania tej nazwy podano w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="030d8-110">Instructions for finding this name are provided later in this topic.</span></span> <span data-ttu-id="030d8-111">>>>(Pyt.: Gdzie są instrukcje?)</span><span class="sxs-lookup"><span data-stu-id="030d8-111">>>>(Q: where are the instructions?)</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="030d8-112">Konfigurowanie zaplecza obrazu</span><span class="sxs-lookup"><span data-stu-id="030d8-112">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="030d8-113">Znajdowanie podstawowego adresu URL multimediów</span><span class="sxs-lookup"><span data-stu-id="030d8-113">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="030d8-114">Aby można było wykonać tę procedurę, należy wykonać kroki opisane w części [Konfigurowanie witryny w usłudze Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="030d8-114">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="030d8-115">Zaloguj się do narzędzia do zarządzania witryną Commerce przy użyciu adresu URL zanotowanego podczas inicjowania usługi e-Commerce w trakcie aprowizacji (zobacz [Inicjowanie usługi e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="030d8-115">Sign in to the Commerce site management tool by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="030d8-116">Otwórz witrynę **Fabrikam** .</span><span class="sxs-lookup"><span data-stu-id="030d8-116">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="030d8-117">W menu po lewej stronie wybierz pozycję **Składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="030d8-117">On the menu on the left, select **Assets**.</span></span>
1. <span data-ttu-id="030d8-118">Wybierz dowolny składnik majątku dla pojedynczego obrazu.</span><span class="sxs-lookup"><span data-stu-id="030d8-118">Select any single image asset.</span></span>
1. <span data-ttu-id="030d8-119">W inspektorze właściwości po prawej stronie znajdź właściwość **Publiczny adres URL**.</span><span class="sxs-lookup"><span data-stu-id="030d8-119">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="030d8-120">Wartość to adres URL.</span><span class="sxs-lookup"><span data-stu-id="030d8-120">The value is a URL.</span></span> <span data-ttu-id="030d8-121">Oto przykład:</span><span class="sxs-lookup"><span data-stu-id="030d8-121">Here is an example:</span></span>

    <span data-ttu-id="030d8-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="030d8-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="030d8-123">Zastąp ostatni identyfikator w adresie URL (**MA1nQC** w poprzednim przykładzie) następującym ciągiem: **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="030d8-123">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="030d8-124">Oto przykładowy adres URL po wprowadzeniu tej zmiany:</span><span class="sxs-lookup"><span data-stu-id="030d8-124">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="030d8-125">Ten adres URL jest podstawowym adresem URL obiektu multimedialnego.</span><span class="sxs-lookup"><span data-stu-id="030d8-125">This URL is your media base URL.</span></span> <span data-ttu-id="030d8-126">Zanotuj go.</span><span class="sxs-lookup"><span data-stu-id="030d8-126">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="030d8-127">Aktualizowanie podstawowego adresu URL obiektu multimedialnego</span><span class="sxs-lookup"><span data-stu-id="030d8-127">Update the media base URL</span></span>

1. <span data-ttu-id="030d8-128">Zaloguj się w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="030d8-128">Sign in to Dynamics 365 Commerce.</span></span>
1. <span data-ttu-id="030d8-129">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail i Commerce \> Ustawienia kanału \> Profile kanału**.</span><span class="sxs-lookup"><span data-stu-id="030d8-129">Use the menu on the left to go to **Modules \> Retail and commerce \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="030d8-130">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="030d8-130">Select **Edit**.</span></span>
1. <span data-ttu-id="030d8-131">W obszarze **Właściwości profilu** zastąp wartość właściwości **Podstawowy adres URL serwera multimediów** utworzonym wcześniej podstawowym adresem URL obiektu multimedialnego.</span><span class="sxs-lookup"><span data-stu-id="030d8-131">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="030d8-132">Wybierz drugi kanał z listy po lewej stronie w obszarze kanału **domyślnego**.</span><span class="sxs-lookup"><span data-stu-id="030d8-132">In the list on the left, under the **Default** channel, select the other channel.</span></span>
1. <span data-ttu-id="030d8-133">W obszarze **Właściwości profilu** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="030d8-133">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="030d8-134">Dla dodanej właściwości wybierz pozycję **Podstawowy adres URL serwera multimediów** jako klucz właściwości.</span><span class="sxs-lookup"><span data-stu-id="030d8-134">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="030d8-135">Jako wartość właściwości wprowadź podstawowy adres URL obiektu multimedialnego, który został utworzony wcześniej.</span><span class="sxs-lookup"><span data-stu-id="030d8-135">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="030d8-136">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="030d8-136">Select **Save**.</span></span>

## <a name="configure-the-email-server"></a><span data-ttu-id="030d8-137">Konfigurowanie serwera poczty e-mail</span><span class="sxs-lookup"><span data-stu-id="030d8-137">Configure the email server</span></span>

> [!NOTE]
> <span data-ttu-id="030d8-138">Wprowadzony tutaj serwer SMTP lub usługa poczty e-mail musi być dostępna z poziomu subskrypcji platformy Azure używanej dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="030d8-138">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="030d8-139">Zaloguj się do aplikacji Commerce.</span><span class="sxs-lookup"><span data-stu-id="030d8-139">Sign in to Commerce.</span></span>
1. <span data-ttu-id="030d8-140">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Administrowanie systemem \> Ustawienia \> Poczta e-mail \> Parametry poczty e-mail**.</span><span class="sxs-lookup"><span data-stu-id="030d8-140">Use the menu on the left to go to **Modules \> System administration \> Setup \> Email \> Email parameters**.</span></span>
1. <span data-ttu-id="030d8-141">Na karcie **Ustawienia SMTP** w polu **Serwer poczty wychodzącej** wprowadź nazwę FQDN lub adres IP serwera SMTP lub usługi poczty e-mail.</span><span class="sxs-lookup"><span data-stu-id="030d8-141">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="030d8-142">W polu **Numer portu SMTP** wprowadź numer portu.</span><span class="sxs-lookup"><span data-stu-id="030d8-142">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="030d8-143">(Jeśli nie korzystasz z protokołu Secure Sockets Layer \[SSL\] domyślnym numerem portu jest **25**).</span><span class="sxs-lookup"><span data-stu-id="030d8-143">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="030d8-144">Jeśli wymagane jest uwierzytelnianie, wprowadź wartości w polach **Nazwa użytkownika** i **Hasło**.</span><span class="sxs-lookup"><span data-stu-id="030d8-144">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="030d8-145">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="030d8-145">Select **Save**.</span></span>
1. <span data-ttu-id="030d8-146">Wybierz pozycję **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="030d8-146">Select **Refresh**.</span></span>
1. <span data-ttu-id="030d8-147">Na karcie **Testowa wiadomość e-mail** w polu **Dostawca poczty e-mail** wybierz pozycję **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="030d8-147">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="030d8-148">W polu **Wyślij do** wprowadź adres e-mail, pod który powinna zostać dostarczona testowa wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="030d8-148">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="030d8-149">Wybierz pozycję **Wyślij testową wiadomość e-mail**.</span><span class="sxs-lookup"><span data-stu-id="030d8-149">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="030d8-150">Konfigurowanie szablonów poczty e-mail</span><span class="sxs-lookup"><span data-stu-id="030d8-150">Configure email templates</span></span>

<span data-ttu-id="030d8-151">Dla każdego zdarzenia transakcyjnego, w ramach którego chcesz wysyłać wiadomości e-mail, musisz zaktualizować szablon wiadomości e-mail za pomocą prawidłowego adresu e-mail nadawcy.</span><span class="sxs-lookup"><span data-stu-id="030d8-151">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="030d8-152">Zaloguj się do aplikacji Commerce.</span><span class="sxs-lookup"><span data-stu-id="030d8-152">Sign in to Commerce.</span></span>
1. <span data-ttu-id="030d8-153">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Administrowanie organizacją \> Ustawienia \> Szablony wiadomości e-mail organizacji**.</span><span class="sxs-lookup"><span data-stu-id="030d8-153">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="030d8-154">Wybierz **Pokaż listę**.</span><span class="sxs-lookup"><span data-stu-id="030d8-154">Select **Show list**.</span></span>
1. <span data-ttu-id="030d8-155">Dla każdego szablonu na liście należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="030d8-155">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="030d8-156">W polu **Adres e-mail nadawcy** wprowadź adres e-mail dla nadawcy.</span><span class="sxs-lookup"><span data-stu-id="030d8-156">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="030d8-157">Opcjonalnie: w polu **Nazwa nadawcy** wprowadź nazwę, która ma być używana jako nazwa nadawcy.</span><span class="sxs-lookup"><span data-stu-id="030d8-157">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="030d8-158">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="030d8-158">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="030d8-159">Dostosowywanie szablonów wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="030d8-159">Customize email templates</span></span>

<span data-ttu-id="030d8-160">Możesz dostosować szablony wiadomości e-mail, tak aby były używane różne obrazy.</span><span class="sxs-lookup"><span data-stu-id="030d8-160">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="030d8-161">Możesz również zaktualizować linki w szablonach, tak aby przenosiły Cię do środowiska wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="030d8-161">Or you might want to update the links in the templates so that they go to your preview environment.</span></span> <span data-ttu-id="030d8-162">W poniższej procedurze opisano sposób pobierania szablonów domyślnych, dostosowywania ich i aktualizowania szablonów w systemie.</span><span class="sxs-lookup"><span data-stu-id="030d8-162">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="030d8-163">W przeglądarce internetowej pobierz [plik zip domyślnych szablonów wiadomości e-mail wersji zapoznawczej aplikacji Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) na komputer lokalny.</span><span class="sxs-lookup"><span data-stu-id="030d8-163">In a web browser, download the [Microsoft Dynamics 365 Commerce Preview default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="030d8-164">Ten plik zawiera następujące dokumenty HTML:</span><span class="sxs-lookup"><span data-stu-id="030d8-164">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="030d8-165">Szablon potwierdzenia zamówienia</span><span class="sxs-lookup"><span data-stu-id="030d8-165">Order confirmation template</span></span>
    - <span data-ttu-id="030d8-166">Wystaw szablon karty upominkowej</span><span class="sxs-lookup"><span data-stu-id="030d8-166">Issue gift card template</span></span>
    - <span data-ttu-id="030d8-167">Szablon nowego zamówienia</span><span class="sxs-lookup"><span data-stu-id="030d8-167">New order template</span></span>
    - <span data-ttu-id="030d8-168">Zapakuj szablon zamówienia</span><span class="sxs-lookup"><span data-stu-id="030d8-168">Pack order template</span></span>
    - <span data-ttu-id="030d8-169">Wybierz szablon zamówienia</span><span class="sxs-lookup"><span data-stu-id="030d8-169">Pick order template</span></span>

1. <span data-ttu-id="030d8-170">Szablony dostosowuje się za pomocą edytora tekstów lub HTML.</span><span class="sxs-lookup"><span data-stu-id="030d8-170">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="030d8-171">Zobacz listę [obsługiwanych tokenów](#supported-tokens-in-the-email-template) w dalszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="030d8-171">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="030d8-172">Zaloguj się do aplikacji Commerce.</span><span class="sxs-lookup"><span data-stu-id="030d8-172">Sign in to Commerce.</span></span>
1. <span data-ttu-id="030d8-173">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Administrowanie organizacją \> Ustawienia \> Szablony wiadomości e-mail organizacji**.</span><span class="sxs-lookup"><span data-stu-id="030d8-173">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="030d8-174">Aby wyświetlić wszystkie szablony, należy rozwinąć listę po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="030d8-174">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="030d8-175">Dla każdego szablonu, który chcesz dostosować, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="030d8-175">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="030d8-176">Wybierz szablon ma liście.</span><span class="sxs-lookup"><span data-stu-id="030d8-176">Select the template in the list.</span></span>
    1. <span data-ttu-id="030d8-177">W obszarze **Zawartość wiadomości e-mail** wybierz odpowiednią wersję językową na liście.</span><span class="sxs-lookup"><span data-stu-id="030d8-177">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="030d8-178">(Domyślny język to **en-us**).</span><span class="sxs-lookup"><span data-stu-id="030d8-178">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="030d8-179">W obszarze **Zawartość wiadomości e-mail** wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="030d8-179">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="030d8-180">Zostanie wyświetlone okienko **Przekaż szablon wiadomości e-mail**.</span><span class="sxs-lookup"><span data-stu-id="030d8-180">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="030d8-181">Wybierz pozycję **Przeglądaj** i znajdź plik HTML, który ma dostosowaną zawartość.</span><span class="sxs-lookup"><span data-stu-id="030d8-181">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="030d8-182">Wybierz pozycję **Przekaż**.</span><span class="sxs-lookup"><span data-stu-id="030d8-182">Select **Upload**.</span></span> <span data-ttu-id="030d8-183">Szablon zostanie przekazany do systemu i zostanie wyświetlony podgląd.</span><span class="sxs-lookup"><span data-stu-id="030d8-183">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="030d8-184">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="030d8-184">Select **OK**.</span></span>
    1. <span data-ttu-id="030d8-185">Opcjonalnie: dostosuj właściwość **Temat** szablonu.</span><span class="sxs-lookup"><span data-stu-id="030d8-185">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="030d8-186">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="030d8-186">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="030d8-187">Obsługiwane tokeny w szablonie wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="030d8-187">Supported tokens in the email template</span></span>

<span data-ttu-id="030d8-188">Podczas renderowania poczty e-mail te tokeny zostaną zastąpione rzeczywistymi wartościami, które dotyczą klienta i jego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="030d8-188">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="030d8-189">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="030d8-189">Sales order</span></span>

<span data-ttu-id="030d8-190">Poniższe tokeny mają zastosowanie do całego zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="030d8-190">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="030d8-191">Nazwa tokena</span><span class="sxs-lookup"><span data-stu-id="030d8-191">Name of the token</span></span> | <span data-ttu-id="030d8-192">Token </span><span class="sxs-lookup"><span data-stu-id="030d8-192">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="030d8-193">Numer zamówienia</span><span class="sxs-lookup"><span data-stu-id="030d8-193">Order number</span></span>      | <span data-ttu-id="030d8-194">%salesid%</span><span class="sxs-lookup"><span data-stu-id="030d8-194">%salesid%</span></span> |
| <span data-ttu-id="030d8-195">Nazwa odbiorcy</span><span class="sxs-lookup"><span data-stu-id="030d8-195">Customer's name</span></span>   | <span data-ttu-id="030d8-196">%customername%</span><span class="sxs-lookup"><span data-stu-id="030d8-196">%customername%</span></span> |
| <span data-ttu-id="030d8-197">Adres dostawy</span><span class="sxs-lookup"><span data-stu-id="030d8-197">Delivery address</span></span>  | <span data-ttu-id="030d8-198">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="030d8-198">%deliveryaddress%</span></span> |
| <span data-ttu-id="030d8-199">Adres do faktury</span><span class="sxs-lookup"><span data-stu-id="030d8-199">Billing address</span></span>   | <span data-ttu-id="030d8-200">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="030d8-200">%customeraddress%</span></span> |
| <span data-ttu-id="030d8-201">Data zamówienia</span><span class="sxs-lookup"><span data-stu-id="030d8-201">Order date</span></span>        | <span data-ttu-id="030d8-202">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="030d8-202">%shipdate%</span></span> |
| <span data-ttu-id="030d8-203">Metoda dostawy</span><span class="sxs-lookup"><span data-stu-id="030d8-203">Delivery mode</span></span>     | <span data-ttu-id="030d8-204">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="030d8-204">%modeofdelivery%</span></span> |
| <span data-ttu-id="030d8-205">Dyskonto</span><span class="sxs-lookup"><span data-stu-id="030d8-205">Discount</span></span>          | <span data-ttu-id="030d8-206">%discount%</span><span class="sxs-lookup"><span data-stu-id="030d8-206">%discount%</span></span> |
| <span data-ttu-id="030d8-207">Podatek</span><span class="sxs-lookup"><span data-stu-id="030d8-207">Sales tax</span></span>         | <span data-ttu-id="030d8-208">%tax%</span><span class="sxs-lookup"><span data-stu-id="030d8-208">%tax%</span></span> |
| <span data-ttu-id="030d8-209">Suma zamówienia</span><span class="sxs-lookup"><span data-stu-id="030d8-209">Order total</span></span>       | <span data-ttu-id="030d8-210">%total%</span><span class="sxs-lookup"><span data-stu-id="030d8-210">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="030d8-211">Wiersz sprzedaży</span><span class="sxs-lookup"><span data-stu-id="030d8-211">Sales line</span></span>

<span data-ttu-id="030d8-212">Dla każdego produktu w zamówieniu następujące tokeny są wypełniane wartościami.</span><span class="sxs-lookup"><span data-stu-id="030d8-212">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="030d8-213">Umieść token **Lista produktów — początek** na początku bloku kodu HTML, który jest powtarzany dla każdego produktu, a token **Lista produktów — koniec** na końcu bloku.</span><span class="sxs-lookup"><span data-stu-id="030d8-213">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="030d8-214">Nazwa tokena</span><span class="sxs-lookup"><span data-stu-id="030d8-214">Name of the token</span></span>      | <span data-ttu-id="030d8-215">Token </span><span class="sxs-lookup"><span data-stu-id="030d8-215">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="030d8-216">Lista produktów - start</span><span class="sxs-lookup"><span data-stu-id="030d8-216">Product list - start</span></span>   | <span data-ttu-id="030d8-217">\<!--%tablebegin.salesline% --\></span><span class="sxs-lookup"><span data-stu-id="030d8-217">\<!--%tablebegin.salesline% --\></span></span> |
| <span data-ttu-id="030d8-218">Lista produktów - koniec</span><span class="sxs-lookup"><span data-stu-id="030d8-218">Product list - end</span></span>     | <span data-ttu-id="030d8-219">\<!--%tableend.salesline%--\></span><span class="sxs-lookup"><span data-stu-id="030d8-219">\<!--%tableend.salesline%--\></span></span> |
| <span data-ttu-id="030d8-220">Nazwa produktu</span><span class="sxs-lookup"><span data-stu-id="030d8-220">Product name</span></span>           | <span data-ttu-id="030d8-221">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="030d8-221">%lineproductname%</span></span> |
| <span data-ttu-id="030d8-222">Opis</span><span class="sxs-lookup"><span data-stu-id="030d8-222">Description</span></span>            | <span data-ttu-id="030d8-223">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="030d8-223">%lineproductdescription%</span></span> |
| <span data-ttu-id="030d8-224">Ilość</span><span class="sxs-lookup"><span data-stu-id="030d8-224">Quantity</span></span>               | <span data-ttu-id="030d8-225">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="030d8-225">%linequantity%</span></span> |
| <span data-ttu-id="030d8-226">Cena wiersza jednostki</span><span class="sxs-lookup"><span data-stu-id="030d8-226">Line unit price</span></span>        | <span data-ttu-id="030d8-227">%lineprice% (sprawdź)</span><span class="sxs-lookup"><span data-stu-id="030d8-227">%lineprice% (verify)</span></span> |
| <span data-ttu-id="030d8-228">Wszystkie pozycje w wierszu</span><span class="sxs-lookup"><span data-stu-id="030d8-228">line item total</span></span>        | <span data-ttu-id="030d8-229">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="030d8-229">%linenetamount%</span></span> |
| <span data-ttu-id="030d8-230">rabat wiersza</span><span class="sxs-lookup"><span data-stu-id="030d8-230">line discount</span></span>          | <span data-ttu-id="030d8-231">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="030d8-231">%linediscount%</span></span> |
| <span data-ttu-id="030d8-232">Data wysyłki</span><span class="sxs-lookup"><span data-stu-id="030d8-232">Ship date</span></span>              | <span data-ttu-id="030d8-233">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="030d8-233">%lineshipdate%</span></span> |
| <span data-ttu-id="030d8-234">Metoda zaopatrzenia</span><span class="sxs-lookup"><span data-stu-id="030d8-234">Procurement method</span></span>     | <span data-ttu-id="030d8-235">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="030d8-235">%linedeliverymode%</span></span> |
| <span data-ttu-id="030d8-236">adres dostawy</span><span class="sxs-lookup"><span data-stu-id="030d8-236">delivery address</span></span>       | <span data-ttu-id="030d8-237">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="030d8-237">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="030d8-238">Jednostka sprzedaży dla wiersza</span><span class="sxs-lookup"><span data-stu-id="030d8-238">Sales unit of the line</span></span> | <span data-ttu-id="030d8-239">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="030d8-239">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="030d8-240">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="030d8-240">Additional resources</span></span>

[<span data-ttu-id="030d8-241">Dynamics 365 Commerce omówienie środowiska wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="030d8-241">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="030d8-242">Inicjuj środowisko wersji zapoznawczej Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="030d8-242">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="030d8-243">Konfiguruj środowisko wersji zapoznawczej usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="030d8-243">Configure a Dynamics 365 Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="030d8-244">Środowisko wersji zapoznawczej Dynamics 365 Commerce— często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="030d8-244">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="030d8-245">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="030d8-245">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="030d8-246">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="030d8-246">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="030d8-247">Portal Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="030d8-247">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="030d8-248">Witryna Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="030d8-248">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
