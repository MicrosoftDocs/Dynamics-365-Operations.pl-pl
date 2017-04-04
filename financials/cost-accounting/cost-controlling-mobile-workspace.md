---
title: Koszt kontroli mobilnych obszaru roboczego Microsoft Dynamics 365 dla operacji aplikacji
description: "Z kosztem Sterowanie roboczego mobilnych, menedżerowie Centrum kosztów można zobaczyć wydajności centrum kosztów zawsze i wszędzie."
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

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Koszt kontroli mobilnych obszaru roboczego Microsoft Dynamics 365 dla operacji aplikacji

Z kosztem Sterowanie roboczego mobilnych, menedżerowie Centrum kosztów można zobaczyć wydajności centrum kosztów zawsze i wszędzie. 

<a name="prerequisites"></a>Wymagania wstępne
-------------

| Wymaganie wstępne                                                         | opis                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przeczytaj na temat usługi Microsoft Dynamics 365 dla operacji platformy mobilnej | [Dynamics 365 dla operacji platformy mobilnej](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 dla operacji                                          | Upewnij się, że używasz środowisku Microsoft Dynamics 365 dla wersji operacji 1611 i Microsoft Dynamics dla platform operacji aktualizacji 3 (listopad 2016). |
| Poprawka KB 3215650                                                    | Zainstaluj poprawkę, aby włączyć obszary robocze, które znajdują się w usłudze Microsoft Dynamics 365 dla operacji.                                                                       |
| Przenośne urządzenie, które ma 365 Dynamics dla operacji zainstalowaną aplikację | Pobierz 365 Dynamics dla operacji aplikacji ze sklepu internetowego.                                                                                                      |

## <a name="introduction"></a>Wprowadzenie
Koszty kontroli mobilnych obszaru roboczego zapewnia natychmiastowy przegląd wydajności bieżącego MPK przez porównanie kosztów rzeczywistych z kosztami budżetowymi. Użytkownik może przejść do stanów kosztów poszczególnych elementów.

### <a name="example"></a>Przykład

Pracownik otrzymuje zaproszenie do międzynarodowej konferencji. Organizacja będzie posiadać na pokrycie kosztów podróży. Pracownik prosi jego Menedżer, jeśli on udziału w konferencji. Zarządca otwiera szybko kosztów kontroli mobilnych obszaru roboczego na jego telefon komórkowy czy ma on budżetu dla pracownika do udziału w konferencji.

### <a name="data-security"></a>Bezpieczeństwo danych

Dane w polu Koszt kontrolowanie obszaru roboczego jest zabezpieczony przez poświadczeń użytkownika. Dyrektor Centrum kosztów jest dozwolona tylko do wyświetlania danych dla własnej MPK. Zabezpieczenia na poziomie dostępu jest zarządzany w module rachunku kosztów. Kosztów księgowych zdefiniować koszt kontrolowanie konfiguracji przenośnych obszar roboczy w module rachunku kosztów. Po opublikowaniu obszaru roboczego do usługi Microsoft Dynamics 365 dla operacji aplikacji jest dostępna w usłudze Dynamics 365 dla operacji aplikacji mobilnej. Gwarantuje to, że wszyscy menedżerowie Centrum kosztów w organizacji spojrzeć na danych w tym samym formacie.

### <a name="actions-views-and-links"></a>Akcje, widoki i łącza

Koszty kontroli mobilnych obszaru roboczego dla usługi Dynamics 365 dla operacji aplikacji zapewnia następujące akcje, widoki i łącza:

-   Akcje 
    -   Wybierz **konfiguracje** wybrać układ.
    -   Wybierz **koszt obiektów** do pobrania centrów kosztów, na których chcesz filtrować dane. **Uwaga:** wyświetlana jest lista według dostępu przyznane w module rachunku kosztów.

<!-- -->

-   Oparte na wybranej w obszarze **akcje** i co to jest skonfigurowany w module rachunku kosztów, można przeglądać następujące informacje na kartach. Należy zauważyć, że kwota ta jest wyświetlana w tym samym formacie: rzeczywiste, budżet, wariancji i odchylenia %. 
    -   Wartości rzeczywiste a budżet (bieżący okres)
    -   Rzeczywiste a budżet skorygowany (bieżący okres)
    -   Wartości rzeczywiste a budżet (poprzedniego okresu)
    -   Rzeczywiste a budżet skorygowany (poprzedniego okresu)
    -   Wartości rzeczywiste a budżet (rok do daty)
    -   Rzeczywiste a budżet skorygowany (rok do daty)

<!-- -->

-   Linki
    -   Szczegóły dla bieżącego okresu.
    -   Szczegółowe informacje dotyczące poprzedniego okresu.
    -   Szczegóły dotyczące od początku roku.

Po wybraniu jednego z łączy jest wyświetlana karta dla każdego elementu kosztów. Kwota w karty jest wyświetlany w następującym formacie: rzeczywiste, budżet, odchylenie budżetu, % odchylenie budżetu, skorygowany budżet, skorygowany odchylenie budżetu i skorygowany budżet odchylenie %.  [![kontrolowanie kosztów](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Rozpocznij
Wykonaj poniższe czynności, aby rozpocząć korzystanie z aplikacji mobilnej kontroli kosztów na urządzeniu przenośnym.

1.  Na sklepu internetowego Pobierz i zainstaluj usługi Microsoft Dynamics 365 dla operacji aplikacji.
2.  Uruchom aplikację na urządzeniu.
3.  Podaj adres URL Dynamics 365.
4.  Wprowadzić firmę do logowania się. Na przykład wpisz **USMF**.
5.  Podczas pierwszego logowania, zostanie wyświetlony monit o nazwę użytkownika i hasło dla sieci Microsoft Dynamics 365 dla konta operacji. Wprowadź swoje poświadczenia. Po zalogowaniu się, można wyświetlić dostępne obszary robocze firmy.

Aby wyświetlić obszary robocze w aplikacji mobilnej, należy najpierw opublikować żądane obszary robocze do 365 Dynamics dla operacji aplikacji.

1.  Uruchom system Dynamics 365 dla operacji.
2.  Przejdź do **Administracja systemu**&gt;**instalacji**&gt;**parametrów systemu**.
3.  Wybierz **Opcje aplikacji mobilnych**.
4.  Wybierz obszar roboczy ** rachunku kosztów ** Aby opublikować mobilnej platformie.
5.  Wybierz **obszaru roboczego opublikować**.
6.  Odśwież swoje urządzenie, aby sprawdzić opublikowanych obszarów roboczych.

## <a name="view-the-performance-of-your-cost-center"></a>Wyświetlanie wydajności centrum kosztów
1.  Na urządzeniu przenośnym, wybierz **rachunku kosztów** obszaru roboczego.
2.  Wybierz **obiektu rachunku kosztów**.
3.  Kliknij **akcje**.
4.  Kliknij **wybierz konfigurację** do wybierz opcję Koszt, kontrolowanie układu.
5.  Click **Done**.
6.  Kliknij **akcje**.
7.  Kliknij **zaznacz obiekt koszt** aby wybrać centrów kosztów, do których przyznano mu uprawnienie dostępu.
8.  Click **Done**.
9.  Umożliwia wyświetlenie ogólną wydajność sieci MPK.
10. Kliknij **szczegóły dotyczące bieżącego okresu**.
11. Wyświetlanie wydajności kosztów poszczególnych elementów.
12. Można także wyszukiwać elementy specyficzny koszt.



