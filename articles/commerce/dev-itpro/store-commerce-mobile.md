---
title: Aplikacja Store Commerce dla platform przenośnych
description: W tym artykule opisano sposób rozpoczęcia korzystania z aplikacji Microsoft Dynamics 365 Commerce Store Commerce dla systemu Android i iOS.
author: stuharg
ms.date: 10/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2018-10-29
ms.openlocfilehash: 1f07a130629863ebd9d036378436cf360e90ac26
ms.sourcegitcommit: 98231ff810f41f9fcdc6b536d87e453028aa6db8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2022
ms.locfileid: "9642344"
---
# <a name="store-commerce-app-for-mobile-platforms"></a>Aplikacja Store Commerce dla platform przenośnych

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób rozpoczęcia korzystania z aplikacji Microsoft Dynamics 365 Commerce Store Commerce dla systemu Android i iOS.

Aplikacje mobilne Dynamics 365 Commerce dla systemu Android i iOS sprawiają, że proces wdrażania w pełni funkcjonalnych urządzeń przenośnych punktu sprzedaży (POS) jest jednoznaczny i prosty. Aplikacje mobilne Store Commerce dostarczają wszystkich możliwości i zalet [aplikacji Store Commerce dla systemu Windows](store-commerce.md) na telefony i tablety. Aplikacje mobilne Store Commerce można instalować bezpośrednio ze sklepów aplikacji Apple i Google Play. Nie wymagają od programisty tworzenia nowego pakietu aplikacji w celu ich wdrożenia lub zaktualizowania. 

Aplikacje mobilne Store Commerce zachowają pełną parzystość funkcji w przypadku bieżących aplikacji hybrydowej Retail. Ponadto system Store Commerce dla systemu iOS zawiera obsługę dedykowanej stacji sprzętowej, dzięki czemu urządzenia iOS mogą komunikować się z sieciowymi terminalami płatności, drukarkami paragonów i szufladami kasowymi bez konieczności wdrażania wspólnej stacji sprzętowej. 

> [!IMPORTANT]
> Aplikacje Store Commerce dla systemu Windows, Android oraz iOS to następna generacja aplikacji punktu sprzedaży dla systemu Dynamics 365 Commerce. Aktualna aplikacja Modern POS (MPOS) oraz [aplikacje hybrydowe Retail](hybridapp.md) dla urządzeń przenośnych będą przestarzałe w październiku 2023 roku. Firma Microsoft zaleca używanie programu Store Commerce lub Cloud POS (CPOS) dla wszystkich nowych wdrożeń punktu sprzedaży. Istniejący klienci powinni dokonać migracji z aplikacji hybrydowej Retail do sklepu Store Commerce. Aby uzyskać więcej informacji dotyczących harmonogramu wycofania dla aplikacji MPOS i aplikacji hybrydowej Retail, zobacz temat [Modernizacja stosu technologicznego w sklepie Dynamics 365 Commerce](https://www.microsoft.com/download/details.aspx?id=103896). 

## <a name="app-architecture"></a>Architektura aplikacji

Aplikacje mobilne Store Commerce używają tej samej topologii, co aplikacja Store Commerce dla systemu Windows, gdy są wdrażane w trybie hybrydowym. Aplikacje mobilne Store Commerce to aplikacje powłokowe, które renderują CPOS bezpośrednio z usługi Commerce Scale Unit (CSU) i łączą się z bezkierunkowym Commerce i Commerce headquarters za pośrednictwem usługi CSU. Model aplikacji powłokowej umożliwia aplikacjom Store Commerce obsługę dedykowanej stacji sprzętowej umożliwiającej bezpośrednią integrację z terminalem płatniczym, drukarką, szufladą kasową i innymi urządzeniami peryferyjnymi. Nie musisz konfigurować wspólnej stacji sprzętowej, aby używać urządzeń sprzętowych. 

Aby zaktualizować aplikację mobilną Store Commerce, wystarczy zaktualizować usługę CSU. Wszystkie nowe funkcje i funkcje punktu sprzedaży zostaną automatycznie pobrane przez aplikację. Aby uzyskać więcej informacji dotyczących sposobu aktualizacji usługi CSU, zobacz temat [Stosowanie aktualizacji i rozszerzeń do usługi Commerce Scale Unit (chmura)](../../fin-ops-core/dev-itpro/deployment/update-retail-channel.md).

Aplikacje powłokowe są serwisowane za pośrednictwem aktualizacji sklepu aplikacji. Gdy wersja pomocnicza osiągnie ogólną dostępność, firma Microsoft opublikuje ją w sklepach aplikacji. Firma Microsoft może również publikować poprawki między wersjami pomocniczymi, aby zwolnić poprawki usterki o wysokim priorytecie.

## <a name="prerequisites"></a>Wymagania wstępne

Aplikacje mobilne Store Commerce wymagają Dynamics 365 Commerce, a w szczególności centrali Commerce headquarters i składników usługi CSU. W poniższej tabeli wymieniono minimalne wersje systemu operacyjnego (OS) i CSU wymagane przez aplikacje mobilne Android i iOS. 

| Wymaganie wstępne | Android      | iOS  |
| ------------ | ------------ | ---- |
| Wersja systemu operacyjnego   | 7.0          | 15.0 |
| Wersja formatu CSU  | 9.38.22266.8 | Do wykonania  |

## <a name="install-the-app"></a>Instalowanie aplikacji

Aplikacje mobilne Store Commerce można zainstalować bezpośrednio ze sklepów Google Play store lub Apple App Store. 

- [Aplikacja Store Commerce dla Android](https://aka.ms/storecommerceandroid)
- Aplikacja Store Commerce dla iOS (wkrótce dostępna)

Pakiety aplikacji Android (.apk) i aplikacji Apple (.ipa) można także pobrać z biblioteki udostępnionych zasobów w usłudze Microsoft Dynamics Lifecycle Services. 

## <a name="device-and-register-setup"></a>Ustawienia urządzenia i kasy

Aby można było uaktywnić kasę w aplikacjach mobilnych sklepu Store Commerce, należy skonfigurować urządzenie i kasę w programie Commerce headquarters. Aby uzyskać więcej informacji, zobacz [Urządzenia i kasy](../implementation-considerations-devices.md). 

### <a name="device-setup"></a>Ustawienia urządzenia

Wykonaj te kroki, aby utworzyć i skonfigurować nowe urządzenie.

1. W Commerce headquarters przejdź do **Retail i Commerce \> Ustawienia kanału \> Ustawienie punktu sprzedaży \> Urządzenia**. 
1. Utwórz nowe urządzenie i wybierz program **Modern POS — Android** lub **Modern POS — iOS** jako typ aplikacji, w zależności od wdrażanych aplikacji przenośnych. 

    > [!NOTE] 
    > Typy aplikacji **Modern POS — Android** i **Modern POS — iOS** są również używane do wdrażania bieżących aplikacji hybrydowej dla systemu Android i iOS. Po zakończeniu wycofania programu MPOS etykiety dla tych typów aplikacji zostaną zaktualizowane do aplikacji **Store Commerce — Android** i **Modern POS — iOS**. 

### <a name="register-setup"></a>Ustawienia rejestru

Można utworzyć nową kasę i skojarzyć ją z utworzonym urządzeniem lub skojarzyć istniejącą kasę z nowym urządzeniem. Aby uzyskać więcej informacji o rejestrach, zobacz temat [Tworzenie i kojarzenie rejestrów](../tasks/create-associate-registers.md).

### <a name="screen-layout-setup"></a>Ustawienie układu ekranu

W przypadku ponownej zmiany układu ekranu uwzględnionego w danych demonstracyjnych dostarczanych z licencją Dynamics 365 Commerce, aplikacja Store Commerce automatycznie wybierze dołączony układ kompaktowy, jeśli rozdzielczość ekranu urządzenia jest mniejsza niż 480 &times; 853 pikseli w orientacji pionowej. Jeśli jednak układ ekranu jest tworzony od podstaw lub urządzenie przenośne korzysta z większej rozdzielczości niż obsługiwana przez układ kompaktowy, należy upewnić się, że zostanie utworzona rozdzielczość i będą skojarzone siatki przycisków odpowiednio do telefonu lub tabletu, w których ma zostać wdrożone rozwiązanie. Aby uzyskać więcej informacji o konfiguracjach układów ekranu, zobacz [konfiguracje graficzne interfejsu użytkownika punktu sprzedaży](../pos-screen-layouts.md). 

Po skonfigurowaniu urządzeń i kas w programie Commerce headquarters przejdź do systemu **Retail i Commerce \> Identyfikator Retail i Commerce \> Harmonogramy dystrybucji** i uruchom zadanie kas.

## <a name="activate-a-device"></a>Aktywuj urządzenie

Aby aktywować urządzenie w aplikacji mobilnej Store Commerce, wykonaj następujące kroki.

1. Otwórz aplikację na urządzeniu przenośnym.
1. Wprowadź adres URL programu CPOS, który można znaleźć na stronie szczegółów środowiska w usłudze Lifecycle Services lub na stronie **Profile kanału** w centrali Commerce headquarters (**Retail i Commerce \> Ustawienia kanału \> Profile kanału**).
1. Zaloguj się, używając poświadczeń pracownika, który ma uprawnienie do zarządzania urządzeniami.
1. Wybierz sklep skojarzony z kasą utworzoną lub ponownie używaną w programie Commerce headquarters.
1. Wybierz kasę skojarzona z utworzonym urządzeniem w programie Commerce headquarters.
1. Urządzenie powinno być teraz aktywowane. Aby zalogować się do kasy, należy użyć identyfikatora operatora i hasła pracownika skojarzonego z wybranym sklepem. 

Aby uzyskać więcej informacji o aktywacji urządzenia, zobacz temat [Aktywacja urządzenia punktu sprzedaży (POS)](retail-device-activation.md#activate-a-modern-pos-or-cloud-pos-device-by-using-guided-activation).

## <a name="feature-parity-with-store-commerce-for-windows"></a>Parzystość funkcji w usługach Store Commerce dla systemu Windows

W poniższej tabeli porównano możliwości aplikacji Store Commerce w różnych platformach Windows, Android i iOS.

| Funkcja                                                                               | Windows | Android | iOS |
| ------------------------------------------------------------------------------------- | ------- | ------- | --- |
| Dedykowana stacja sprzętowa                                                            | Tak     | Tak     | Tak |
| Wspólna stacja sprzętowa                                                               | Tak     | Tak     | Tak |
| Komunikacja z sieciowym urządzeniem peryferyjnym (terminal płatności, drukarka i szuflada kasowa) | Tak     | Tak     | Tak |
| Urządzenia peryferyjne OLE for Point of Sale (OPOS) za pośrednictwem lokalnej stacji sprzętowej             | Tak     | Nr      | Nr  |
| Tryb offline                                                                          | Tak     | Nr      | Nr  |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Aplikacja Store Commerce](store-commerce.md)

[Wybierz między rozwiązaniem Store Commerce i Cloud POS](../mpos-or-cpos.md)

[Rozwiązywanie problemów z konfiguracją i instalacją Store Commerce](../troubleshoot/store-commerce-setup-installation.md)
