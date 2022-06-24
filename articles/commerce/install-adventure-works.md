---
title: Instalacja motywu Adventure Works
description: W tym artykule opisano sposób zainstalowania motywu Adventure Works w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 18c2612b8b6b4ed8195ff8e71d6e0495f7e80950
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854907"
---
# <a name="install-the-adventure-works-theme"></a>Instalacja motywu Adventure Works

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób zainstalowania motywu Adventure Works w Microsoft Dynamics 365 Commerce. 

> [!IMPORTANT]
> Motyw Adventure Works i moduły są dostępne od wersji Dynamics 365 Commerce 10.0.20. Są one dostępne w Microsoft AppSource.

## <a name="prerequisites"></a>Wymagania wstępne

Zanim zainstalujesz motyw Adventure Works, musisz mieć środowisko Dynamics 365 Commerce (Commerce w wersji 10.0.20 lub nowszej), które zawiera Retail Cloud Scale Unit (RCSU), Commerce Online Software Development Kit (SDK) i bibliotekę modułu Commerce. Aby uzyskać informacje o tym, jak zainstalować pakiet Commerce SDK i bibliotekę modułów, zobacz [Konfigurowanie środowiska developmentu](e-commerce-extensibility/setup-dev-environment.md). 

## <a name="installation-steps"></a>Kroki instalacji

### <a name="install-the-adventure-works-theme-in-your-application"></a>Zainstaluj kompozycję Adventure Works w aplikacji

Pakiet motywów Adventure Works jest dostępny w pliku danych **dynamics365-commerce** jako **@msdyn365-commerce-theme/adventureworks-theme-kit**. Jednak mimo że pakiet motywów Adventure Works jest częścią tego źródła, znajduje się w innej przestrzeni nazw. Dlatego należy wykonać następujące kroki, aby dodać wpisy rejestru dla obszaru nazw.

1. Zaktualizuj plik **.npmrc**, aby zawierał następujący wpis rejestru (jeśli wpis nie jest jeszcze uwzględniony):

    `@msdyn365-commerce-theme:registry=https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/`

1. Zaktualizuj plik **.yarnrc**, aby zawierał następujący wpis rejestru (jeśli wpis nie jest jeszcze uwzględniony):

    `"@msdyn365-commerce-theme:registry" "https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/"`  
    
Aby zainstalować pakiet w środowisku lokalnym, uruchom polecenie `yarn add THEME_PACKAGE@VERSION` z wiersza polecenia, gdzie **THEME_PACKAGE** jest pakietem motywu (@msdyn365-commerce-theme/adventureworks-theme-kit), a **VERSION** jest numerem wersji używanej biblioteki modułów. Bardzo ważne jest, aby wersje pakietu motywu i biblioteki modułów były takie same. Aby znaleźć poprawny numer wersji biblioteki modułów do użycia, otwórz plik package.json i odszukaj wartość **starter-pack** w sekcji **zależności**. W poniższym przykładzie plik package.json używa biblioteki modułów w wersji 9.32, która mapuje się na wersję Dynamics 365 Commerce 10.0.22.  

```json
"dependencies": {
    "@msdyn365-commerce-modules/starter-pack": "9.32",
}
```

W poniższym przykładzie pokazano, jak uruchomić polecenie `yarn add`, aby dodać wersję 9.32 motywu „Adventure Works”. Polecenie automatycznie aktualizuje plik package.json, aby zawierał zależność.

`yarn add @msdyn365-commerce-theme/adventureworks-theme-kit@9.32`

Aby uzyskać więcej informacji na temat aktualizacji wersji biblioteki modułów, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md). 

> [!IMPORTANT]
> - Wersja motywu powinna być zgodna z wersją biblioteki modułów, aby zapewnić, że wszystkie funkcje działają zgodnie z oczekiwaniami. 
> - Minimalna wersja dla biblioteki modułu Commerce i SDK powinna wynosić 10.0.20 (9.31). 

### <a name="add-the-font-files-for-the-adventure-works-theme"></a>Dodaj pliki czcionek do motywu Adventure Works

Po zainstalowaniu motywu Adventure Works w aplikacji należy dodać wymagane pliki czcionek. Aby wykonać ten krok, skopiuj wszystkie pliki czcionek z **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\public\webfonts** do ścieżki katalogu publicznego aplikacji partnerskiej **\public\webfonts**.

### <a name="set-up-the-resources-for-the-adventure-works-theme"></a>Skonfiguruj zasoby dla motywu Adventure Works

Następnym krokiem jest aktualizacja wymaganego zasobu domyślnego dla motywu. Aby wykonać ten krok, skopiuj zawartość z pliku global.json z folderu **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\resources\modules** do aplikacji partnerskiej global Plik .json w folderze **\src\resources\modules**. Jeśli katalog docelowy **\src\resources** nie istnieje, można go skopiować w całości z katalogu źródłowego **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks** do katalogu docelowego **\src**.

### <a name="pull-updates-and-validate-the-theme"></a>Ściągnij aktualizacje i sprawdź poprawność motywu

Aby uzyskać informacje o tym, jak pobrać najnowsze pakiety SDK, bibliotekę modułów i inne aktualizacje zależności, zobacz sekcję „Wyciągnij aktualizacje” w [SDK i aktualizacje biblioteki modułów](e-commerce-extensibility/sdk-updates.md#pull-updates).

Po ściągnięciu najnowszych zależności możesz uruchomić polecenie **yarn start**, aby uruchomić serwer Node w swoim środowisku programistycznym i przetestować nowy motyw Adventure Works. Przeglądać aplikację lokalnie przy użyciu parametru ciągu zapytania `?theme=adventureworks` (na przykład `https://localhost:4000/?theme=adventureworks`).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Motyw Adventure Works](adventure-works-theme.md)

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
