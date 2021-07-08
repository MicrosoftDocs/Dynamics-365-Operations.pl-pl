---
title: Nowości lub zmiany w aplikacji mobilnej Warehouse Management
description: W tym temacie wymieniono nowe i zmienione funkcje dla każdej wydanej wersji aplikacji mobilnej Warehouse Management dla firmy Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261794"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="e122b-103">Nowości lub zmiany w aplikacji mobilnej Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="e122b-103">What's new or changed in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e122b-104">W tym temacie wymieniono nowe funkcje, poprawki, ulepszenia i znane problemy dla każdej wydanej wersji aplikacji mobilnej Warehouse Management w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e122b-104">This topic lists new features, fixes, improvements, and known issues for each released version of the Warehouse Management mobile app for Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="version-2060"></a><span data-ttu-id="e122b-105">Wersja 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="e122b-105">Version 2.0.6.0</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2060"></a><span data-ttu-id="e122b-106">Nowe funkcje, poprawki i ulepszenia w wersji 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="e122b-106">New features, fixes, and improvements in version 2.0.6.0</span></span>

<span data-ttu-id="e122b-107">Ta wersja wprowadza następujące nowe funkcje, poprawki i ulepszenia:</span><span class="sxs-lookup"><span data-stu-id="e122b-107">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="e122b-108">Tryb demonstracyjny pokazuje teraz wszystkie etykiety w języku urządzenia.</span><span class="sxs-lookup"><span data-stu-id="e122b-108">Demo mode now shows all labels in the device language.</span></span>
- <span data-ttu-id="e122b-109">Jest mniej prawdopodobne, że otrzymasz następujący komunikat o błędzie: „Nie można znaleźć odpowiedniego widoku dla określonego rozmiaru.”</span><span class="sxs-lookup"><span data-stu-id="e122b-109">You're less likely to receive the following error message: "Cannot find a suitable view for the specified size."</span></span>
- <span data-ttu-id="e122b-110">Zwiększono minimalną wysokość dla kart pracy (dla przypadków, gdy na liście pracy mają się pojawić trzy lub mniej pól).</span><span class="sxs-lookup"><span data-stu-id="e122b-110">The minimum height for work cards has been increased (for cases where three or fewer fields are configured to appear in the work list).</span></span>
- <span data-ttu-id="e122b-111">Poprawiono marginesy (wygaszanie) na dole kart szczegółów.</span><span class="sxs-lookup"><span data-stu-id="e122b-111">Margins (fade out) at the bottom of details cards have been improved.</span></span>
- <span data-ttu-id="e122b-112">Nieprawidłowe symbole w plikach XML, które są wymieniane z serwerem, są teraz obsługiwane z wdziękiem.</span><span class="sxs-lookup"><span data-stu-id="e122b-112">Invalid symbols in XML files that are exchanged with the server are now handled gracefully.</span></span> <span data-ttu-id="e122b-113">(Na przykład, znaki niedrukowalne są teraz obsługiwane z wdziękiem i nie powodują już, że aplikacja przestaje odpowiadać).</span><span class="sxs-lookup"><span data-stu-id="e122b-113">(For example, non-printable characters are now handled gracefully and no longer cause the app to stop responding.)</span></span>
- <span data-ttu-id="e122b-114">Błędy HTTP (takie jak „błąd 503”), gdy żądanie serwera jest wysyłane, są teraz obsługiwane z wdziękiem.</span><span class="sxs-lookup"><span data-stu-id="e122b-114">HTTP errors (such as "error 503") when a server request is submitted are now handled gracefully.</span></span>
- <span data-ttu-id="e122b-115">Podczas wyświetlania błędu lista opcji nie jest już automatycznie wyświetlana dla kontrolek pola kombi.</span><span class="sxs-lookup"><span data-stu-id="e122b-115">While an error is being shown, the options list is no longer automatically shown for combo box controls.</span></span>
- <span data-ttu-id="e122b-116">Aplikacja nie przestaje odpowiadać z powodu orientacji wyświetlacza wybranej w ustawieniach użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e122b-116">The app no longer stops responding because of the display orientation that is selected in user settings.</span></span>
- <span data-ttu-id="e122b-117">Obrazy produktów są teraz wyświetlane w środowiskach samoobsługowych.</span><span class="sxs-lookup"><span data-stu-id="e122b-117">Product images are now shown in self-service environments.</span></span> <span data-ttu-id="e122b-118">(Ta zmiana dotyczy tylko wersji o niskiej rozdzielczości.</span><span class="sxs-lookup"><span data-stu-id="e122b-118">(This change applies to low-resolution versions only.</span></span> <span data-ttu-id="e122b-119">Usługa zarządzania plikami nie obsługuje pełnowymiarowych obrazów w środowiskach samoobsługowych).</span><span class="sxs-lookup"><span data-stu-id="e122b-119">The file management service doesn't support full-sized images in self-service environments.)</span></span>
- <span data-ttu-id="e122b-120">Usunięto problem związany z krótkim pobieraniem o zerowej ilości.</span><span class="sxs-lookup"><span data-stu-id="e122b-120">An issue that involved zero-quantity short picks has been fixed.</span></span>
- <span data-ttu-id="e122b-121">Aplikacja nie przestaje odpowiadać, gdy na karcie szczegółów znajduje się wiele identycznych pól.</span><span class="sxs-lookup"><span data-stu-id="e122b-121">The app no longer stops responding when a details card shows multiple identical fields.</span></span>

### <a name="known-issues-in-version-2060"></a><span data-ttu-id="e122b-122">Znane problemy w wersji 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="e122b-122">Known issues in version 2.0.6.0</span></span>

<span data-ttu-id="e122b-123">W tej wersji występują następujące znane problemy:</span><span class="sxs-lookup"><span data-stu-id="e122b-123">The following known issues exist in this version:</span></span>

- <span data-ttu-id="e122b-124">Aplikacja (zwłaszcza lista prac) z czasem staje się wolniejsza.</span><span class="sxs-lookup"><span data-stu-id="e122b-124">The app (especially the work list) becomes slower over time.</span></span>
- <span data-ttu-id="e122b-125">**Wersja dla systemu Windows:** Gdy USB gun jest używany do skanowania w systemie Windows, niespójne wyniki powodują mieszanie zeskanowanych symboli.</span><span class="sxs-lookup"><span data-stu-id="e122b-125">**Windows version:** When a USB gun is used for scanning on Windows, inconsistent results cause scanned symbols to be mixed up.</span></span>

## <a name="version-2050"></a><span data-ttu-id="e122b-126">Wersja 2.0.5.0</span><span class="sxs-lookup"><span data-stu-id="e122b-126">Version 2.0.5.0</span></span>

<span data-ttu-id="e122b-127">Ta wersja wprowadza następujące nowe funkcje, poprawki i ulepszenia:</span><span class="sxs-lookup"><span data-stu-id="e122b-127">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="e122b-128">Sekret klienta nie jest już ukryty w ustawieniach połączenia.</span><span class="sxs-lookup"><span data-stu-id="e122b-128">The client secret is no longer hidden in the connection settings setup.</span></span>
- <span data-ttu-id="e122b-129">Możesz teraz długo nacisnąć na dowolny tekst, aby zobaczyć go w całości.</span><span class="sxs-lookup"><span data-stu-id="e122b-129">You can now long-press on any text to see it fully.</span></span>
- <span data-ttu-id="e122b-130">Poprawiono komunikat o błędzie w przypadku braku uprawnień do przechowywania danych.</span><span class="sxs-lookup"><span data-stu-id="e122b-130">The error message when storage permissions are missing has been improved.</span></span>
- <span data-ttu-id="e122b-131">Dla niektórych przepływów dodano nowe sekwencje sterujące.</span><span class="sxs-lookup"><span data-stu-id="e122b-131">New control sequences have been added for some flows.</span></span>
- <span data-ttu-id="e122b-132">Przycisk wysyłania nie jest już nieprawidłowo dostępny ze względu na rozmiar okna.</span><span class="sxs-lookup"><span data-stu-id="e122b-132">The submit button no longer incorrectly becomes available because of the window size.</span></span>
- <span data-ttu-id="e122b-133">Suwaki mogą teraz działać na mniejszych ekranach, gdy używane są większe rozmiary przycisków.</span><span class="sxs-lookup"><span data-stu-id="e122b-133">Sliders can now proceed on smaller screens when larger button sizes are used.</span></span>
- <span data-ttu-id="e122b-134">Nakładka na cztery przyciski nie jest już ucięta.</span><span class="sxs-lookup"><span data-stu-id="e122b-134">The four-button overlay is no longer cut off.</span></span>
- <span data-ttu-id="e122b-135">Klawiatura obsługuje teraz przycisk usuwania.</span><span class="sxs-lookup"><span data-stu-id="e122b-135">The keyboard now supports the delete button.</span></span>
- <span data-ttu-id="e122b-136">Usunięto problem z jasnością, który mógł wystąpić po naciśnięciu klawiatury.</span><span class="sxs-lookup"><span data-stu-id="e122b-136">A brightness issue that could occur when the keyboard is pressed has been fixed.</span></span>
- <span data-ttu-id="e122b-137">Naprawiono różne problemy z danymi demo.</span><span class="sxs-lookup"><span data-stu-id="e122b-137">Various demo data issues have been fixed.</span></span>
- <span data-ttu-id="e122b-138">Naprawiono błąd, który dotyczył pól numerycznych na stronie szczegółów.</span><span class="sxs-lookup"><span data-stu-id="e122b-138">An issue that affected numeric fields on the details page has been fixed.</span></span>
- <span data-ttu-id="e122b-139">Klawiatura ekranowa nie znika już czasami na niektórych urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="e122b-139">The screen keyboard no longer occasionally disappears on some devices.</span></span>
- <span data-ttu-id="e122b-140">Naprawiono różne błędy interfejsu użytkownika (UI), takie jak błędy, które wpływały na kolor tła i pozycjonowanie.</span><span class="sxs-lookup"><span data-stu-id="e122b-140">Various user interface (UI) bugs have been fixed, such as bugs that affected the background color and positioning.</span></span>
- <span data-ttu-id="e122b-141">Ulepszono interfejs użytkownika w języku rosyjskim.</span><span class="sxs-lookup"><span data-stu-id="e122b-141">The Russian-language UI has been improved.</span></span>
- <span data-ttu-id="e122b-142">Naprawiono różne problemy, które powodowały, że system przestawał odpowiadać.</span><span class="sxs-lookup"><span data-stu-id="e122b-142">Various issues that caused the system to stop responding have been fixed.</span></span>
- <span data-ttu-id="e122b-143">Usunięto problem związany z ponownym otwieraniem kalkulatora.</span><span class="sxs-lookup"><span data-stu-id="e122b-143">An issue that was related to reopening the calculator has been fixed.</span></span>
- <span data-ttu-id="e122b-144">**Wersja Android:** Rozwiązano problem, który powodował, że Android 4.4 przestał odpowiadać podczas uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="e122b-144">**Android version:** An issue that caused Android 4.4 to stop responding on startup has been fixed.</span></span>
- <span data-ttu-id="e122b-145">**Wersja Android** Minimalne skalowanie zostało zmniejszone do 50 procent.</span><span class="sxs-lookup"><span data-stu-id="e122b-145">**Android version:** Minimum scaling has been reduced to 50 percent.</span></span>

## <a name="version-2040"></a><span data-ttu-id="e122b-146">Wersja 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="e122b-146">Version 2.0.4.0</span></span>

<span data-ttu-id="e122b-147">Wersja 2.0.4.0 była pierwszym ogólnie dostępnym wydaniem aplikacji mobilnej Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="e122b-147">Version 2.0.4.0 was the first generally available release of the Warehouse Management mobile app.</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2040"></a><span data-ttu-id="e122b-148">Nowe funkcje, poprawki i ulepszenia w wersji 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="e122b-148">New features, fixes, and improvements in version 2.0.4.0</span></span>

<span data-ttu-id="e122b-149">Ta wersja wprowadza następujące nowe funkcje, poprawki i ulepszenia, które nie były dostępne w wersji zapoznawczej:</span><span class="sxs-lookup"><span data-stu-id="e122b-149">This version introduces the following new features, fixes, and improvements that weren't available in the preview version:</span></span>

- <span data-ttu-id="e122b-150">Jeśli na karcie szczegółów znajdują się dwie etykiety z identycznymi danymi, jedna z nich jest ukryta.</span><span class="sxs-lookup"><span data-stu-id="e122b-150">If a details card includes two labels that have identical data, one of the labels is hidden.</span></span>
- <span data-ttu-id="e122b-151">Znaki specjalne są teraz wyświetlane domyślnie, a opcja ich ukrywania została usunięta z ustawień użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e122b-151">Special characters are now shown by default, and the option to hide them has been removed from user settings.</span></span>
- <span data-ttu-id="e122b-152">Wyłączone przyciski wysyłania są teraz wyświetlane jako niedostępne w widoku kompaktowym z ręki.</span><span class="sxs-lookup"><span data-stu-id="e122b-152">Disabled submit buttons are now shown as unavailable in compact arm-held view.</span></span>
- <span data-ttu-id="e122b-153">Zmiana w logice sekwencjonowania elementów sterujących zapewnia płynniejsze skalowanie w różnych urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="e122b-153">A change to the sequencing logic for controls ensures smoother scaling across devices.</span></span> <span data-ttu-id="e122b-154">Dzięki temu nie ma potrzeby dostosowywania skalowania czcionek czy przycisków.</span><span class="sxs-lookup"><span data-stu-id="e122b-154">Therefore, there is less need to adjust the scaling of fonts or buttons.</span></span>
- <span data-ttu-id="e122b-155">Domyślny motyw kolorów został zmieniony na *Ciemny*.</span><span class="sxs-lookup"><span data-stu-id="e122b-155">The default color theme has been changed to *Dark*.</span></span>
- <span data-ttu-id="e122b-156">Brakująca ikona dla wyłączonego przycisku wysyłania została dodana w widoku wstążki.</span><span class="sxs-lookup"><span data-stu-id="e122b-156">The missing icon for the disabled submit button has been added in ribbon view.</span></span>
- <span data-ttu-id="e122b-157">Wyjątki przekroczenia limitu czasu przenoszą teraz użytkownika na stronę połączenia zamiast pokazywać błąd w linii.</span><span class="sxs-lookup"><span data-stu-id="e122b-157">Time-out exceptions now take you to the connection page instead of showing an in-line error.</span></span>
- <span data-ttu-id="e122b-158">Jeśli nie ma dostępnej akcji przesyłania (np. **OK**, **Tak**, **Zaakceptowana**, **Zakończona** lub **Zakończona**), przycisk przesyłania będzie wyłączony.</span><span class="sxs-lookup"><span data-stu-id="e122b-158">If no submit action is available (such as **OK**, **Yes**, **Accept**, **Done**, or **Finished**), the submit button will be disabled.</span></span>
- <span data-ttu-id="e122b-159">Poprawiono stabilność aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e122b-159">App stability has been improved.</span></span>
- <span data-ttu-id="e122b-160">Istnieje poprawka zagrożeń dla bezpieczeństwa [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span><span class="sxs-lookup"><span data-stu-id="e122b-160">There is a fix for security vulnerability [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span></span>
- <span data-ttu-id="e122b-161">**Wersja systemu Windows:** Naprawiono problem występujący w systemie Windows, w którym menu nie reagowało po zmianie rozmiaru okna.</span><span class="sxs-lookup"><span data-stu-id="e122b-161">**Windows version:** An issue on Windows, where menus were unresponsive after the window was resized, has been fixed.</span></span>

### <a name="known-issue-in-version-2040"></a><span data-ttu-id="e122b-162">Znane problemy w wersji 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="e122b-162">Known issue in version 2.0.4.0</span></span>

<span data-ttu-id="e122b-163">W tej wersji występuje następujący znany problem:</span><span class="sxs-lookup"><span data-stu-id="e122b-163">The following known issue exists in this version:</span></span>

- <span data-ttu-id="e122b-164">Ta wersja stanowi problem z urządzeniami, które korzystają z Android w wersji 4.4.</span><span class="sxs-lookup"><span data-stu-id="e122b-164">This version has an issue with devices that use Android 4.4.</span></span> <span data-ttu-id="e122b-165">Podczas korzystania z aplikacji w tej wersji Android mogą wystąpić problemy.</span><span class="sxs-lookup"><span data-stu-id="e122b-165">You might experience issues when you use the app on this Android version.</span></span>
