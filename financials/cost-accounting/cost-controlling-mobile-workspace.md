---
title: "Mobilny obszar roboczy Kontrola kosztów dla aplikacji Microsoft Dynamics 365 for Operations"
description: "W mobilnym obszarze roboczym Kontrola kosztów menedżerowie centrów kosztów mają podgląd na działanie tych centów zawsze i wszędzie."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 53 - 04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 84740472-494f-444c-9b74-f83b7342fd25
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 8136efb1d2669c39fcc0f80b60e80ecae983d5d8
ms.lasthandoff: 03/31/2017


---

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Mobilny obszar roboczy Kontrola kosztów dla aplikacji Microsoft Dynamics 365 for Operations

W mobilnym obszarze roboczym Kontrola kosztów menedżerowie centrów kosztów mają podgląd na działanie tych centów zawsze i wszędzie. 

<a name="prerequisites"></a>Wymagania wstępne
-------------

| Wymaganie wstępne                                                         | opis                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przeczytaj na temat platformy mobilnej Microsoft Dynamics 365 for Operations | [Platforma komórkowa Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Upewnij się, że używasz środowiska, w którym zainstalowano program Microsoft Dynamics 365 for Operations w wersji 1611 oraz aktualizację nr 3 platformy Microsoft Dynamics 365 for Operations (z listopada 2016 r.). |
| Poprawka KB 3215650                                                    | Zainstaluj poprawkę, która włączy obsługę obszarów roboczych zawartych w usłudze Microsoft Dynamics 365 for Operations.                                                                       |
| Urządzenie przenośne, które ma zainstalowaną aplikację Dynamics 365 for Operations | Pobierz aplikację Dynamics 365 for Operations ze sklepu z aplikacjami dla urządzeń komórkowych.                                                                                                      |

## <a name="introduction"></a>Wprowadzenie
Mobilny obszar roboczy Kontrola kosztów zapewnia natychmiastowy podgląd wyników działania centrów kosztów poprzez porównanie kosztów rzeczywistych z kosztami budżetowymi. W widoku można przechodzić do stanów poszczególnych składników kosztów.

### <a name="example"></a>Przykład

Pracownik otrzymuje zaproszenie na międzynarodową konferencję. Organizacja musi pokryć wszystkie koszty podróży. Pracownik pyta przełożonego, czy może wziąć udział w konferencji. Przełożony szybko otwiera mobilny obszar roboczy Kontrola kosztów na swoim telefonie komórkowym i sprawdza, czy ma budżet na pokrycie kosztów udziału pracownika w konferencji.

### <a name="data-security"></a>Bezpieczeństwo danych

Dane w obszarze roboczym Kontrola kosztów są zabezpieczone poświadczeniami użytkownika. Menedżer centrum kosztów ma pozwolenie na wgląd tylko w dane swojego centrum kosztów. Zabezpieczenia na poziomie dostępu są administrowane w module Rachunek kosztów. Księgowi kosztów definiują konfigurację mobilnego obszaru roboczego Kontrola kosztów w module Rachunek kosztów. Po opublikowaniu obszaru roboczego w aplikacji Microsoft Dynamics 365 for Operations jest on dostępny w aplikacji komórkowej Dynamics 365 for Operations. Gwarantuje to, że wszyscy menedżerowie centrów kosztów w organizacji widzą dane w tym samym formacie.

### <a name="actions-views-and-links"></a>Akcje, widoki i łącza

Mobilny obszar roboczego Kontrola kosztów dla aplikacji Dynamics 365 for Operations oferuje następujące akcje, widoki i łącza:

-   Akcje 
    -   Kliknij opcję **Konfiguracje**, aby wybrać układ.
    -   Kliknij opcję **Obiekty kosztów**, aby wybrać centra kosztów, z których chcesz filtrować dane. **Uwaga:** Lista jest wyświetlana zgodnie z uprawnieniami dostępu przyznanymi w module Rachunek kosztów.

<!-- -->

-   Na podstawie ustawień wybranych w obszarze **Akcje** i skonfigurowanych w module Rachunek kosztów można przeglądać poniższe informacje na kartach. Należy zauważyć, że kwota jest wyświetlana w tym samym formacie: wartości rzeczywiste, budżet, odchylenie i % odchylenia. 
    -   Wartości rzeczywiste a budżet (bieżący okres)
    -   Wartości rzeczywiste a skorygowany budżet (bieżący okres)
    -   Wartości rzeczywiste a budżet (poprzedni okres)
    -   Wartości rzeczywiste a skorygowany budżet (poprzedni okres)
    -   Wartości rzeczywiste a budżet (od początku roku)
    -   Wartości rzeczywiste a skorygowany budżet (od początku roku)

<!-- -->

-   Linki
    -   Szczegóły bieżącego okresu.
    -   Szczegóły poprzedniego okresu.
    -   Szczegóły okresu od początku roku.

Po wybraniu jednego z łączy jest wyświetlana karta dla każdego składnika kosztów. Kwota na karcie jest wyświetlana w następującym formacie: wartości rzeczywiste, budżet, odchylenie budżetu, % odchylenia budżetu, skorygowany budżet, odchylenie skorygowanego budżetu i % odchylenia skorygowanego budżetu.  [![cost-controlling](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Rozpocznij
Wykonaj poniższe czynności, aby rozpocząć korzystanie z mobilnej aplikacji kontroli kosztów na swoim urządzeniu przenośnym.

1.  W sklepie z aplikacjami dla urządzeń komórkowych pobierz i zainstaluj aplikację Microsoft Dynamics 365 for Operations.
2.  Uruchom aplikację na urządzeniu.
3.  Wprowadź adres URL usługi Dynamics 365.
4.  Wpisz firmę, do której chcesz się zalogować. Na przykład wpisz **USMF**.
5.  Podczas pierwszego logowania zostanie wyświetlony monit o podanie nazwy użytkownika i hasła dostępu do konta programu Microsoft Dynamics 365 for Operations. Wprowadź swoje poświadczenia. Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy.

Aby widzieć obszary robocze w aplikacji mobilnej, należy najpierw opublikować żądane obszary w aplikacji Dynamics 365 for Operations.

1.  Uruchom program Dynamics 365 for Operations.
2.  Wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **Parametry systemu**.
3.  Wybierz opcję **Zarządzaj aplikacją mobilną**.
4.  Wybierz obszar roboczy **Kontrola kosztów**, aby go opublikować na platformie mobilnej.
5.  Wybierz opcję **Opublikuj obszar roboczy**.
6.  Odśwież swoje urządzenie, a zobaczysz opublikowane obszary robocze.

## <a name="view-the-performance-of-your-cost-center"></a>Wyświetlanie wyników działania centrum kosztów
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Kontrola kosztów**.
2.  Wybierz opcję **Kontrola obiektów kosztów**.
3.  Kliknij opcję **Akcje**.
4.  Kliknij opcję **Wybierz konfigurację** i wybierz układ kontroli kosztów.
5.  Kliknij przycisk **Gotowe**.
6.  Kliknij opcję **Akcje**.
7.  Kliknij opcję **Wybierz obiekt kosztu** i zaznacz centra kosztów, do których przyznano Ci uprawnienie dostępu.
8.  Kliknij przycisk **Gotowe**.
9.  Wyświetl całościowe wyniki działania centrum kosztów.
10. Kliknij opcję **Szczegóły bieżącego okresu**.
11. Wyświetl wyniki działania poszczególnych składników kosztów.
12. Można także wyszukiwać konkretne składniki kosztów.



