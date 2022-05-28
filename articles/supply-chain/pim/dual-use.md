---
title: Towary podwójnego zastosowania
description: W tym temacie wyjaśniono, jak śledzić produkty zidentyfikowane jako towary podwójnego zastosowania, przechowywać numery certyfikatów dla każdego odpowiedniego produktu i kraju przeznaczenia, a także drukować ważne numery certyfikatów na odpowiednich fakturach, dokumentach dostawy i/lub zamówieniach sprzedaży.
author: t-benebo
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: COODualUseCerts, COORules, COODualUseCountries
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 787d0c4ebcf83d6bfec05943f2bb0ddc5961a93a
ms.sourcegitcommit: e18ea2458ae042b7d83f5102ed40140d1067301a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2022
ms.locfileid: "8736041"
---
# <a name="dual-use-goods"></a>Towary podwójnego zastosowania

[!include [banner](../includes/banner.md)]

Towary podwójnego zastosowania to zazwyczaj towary, które mają zarówno zastosowania cywilne, jak i wojskowe. Na przykład substancja chemiczna może być stosowana albo jako nawóz, albo jako materiał wybuchowy. Wiele krajów ma specjalne regulacje dotyczące eksportowania, importowania i transportu produktów podwójnego zastosowania. Dlatego ważne jest, aby firmy uczestniczące w międzynarodowym handlu towarami podwójnego zastosowania śledziły różne zasady i certyfikaty.

Funkcja podwójnego zastosowania pomaga firmom śledzić produkty zidentyfikowane jako towary podwójnego zastosowania, przechowuje numery certyfikatów dla każdego odpowiedniego produktu i kraju docelowego oraz drukuje ważne numery certyfikatów na odpowiednich fakturach, listach przewozowych i/lub zamówieniach sprzedaży. Dzięki temu, gdy produkty są wysyłane, zawsze uwzględniają aktualne certyfikaty.

Rozważmy następujący scenariusz:

1. Strona **Konfiguracja kraju dla podwójnego zastosowania** w systemie wskazuje, że wysyłki do Francji wymagają certyfikacji.
2. Strona **Szczegóły zwolnionego produktu** dla produktu X-100 wskazuje, że jest to produkt podwójnego zastosowania. Kod, Kategoria, Grupa i system wskazują klasyfikację kontroli eksportu, do której należy dany produkt.
3. Strona **Certyfikaty podwójnego zastosowania** zawiera certyfikat dla produktu X-100, który jest wysyłany do Francji. Certyfikat wygasa 1 stycznia 2020.
4. W dniu 17 czerwca 2020 r. Tworzysz zamówienie sprzedaży dla firmy klienta z siedzibą we Francji, a zamówienie obejmuje produkt X-100.
5. Po potwierdzeniu zamówienia sprzedaży system określa następujące informacje:

    1. Czy zamówienie obejmuje produkty podwójnego zastosowania?
    2. Jeśli zamówienie zawiera towary podwójnego zastosowania, czy kraj docelowy wymaga certyfikatów podwójnego zastosowania?
    3. Jeśli kraj wymaga certyfikatów o podwójnym użyciu, czy istnieje ważny certyfikat dla każdego towaru podwójnego zastosowania dla kraju docelowego?

6. Zamówienie obejmuje produkt X-100, produkt jest wysyłany do Francji, a dla produktu istnieje certyfikat francuski. Jednak certyfikat wygasł. Dlatego wyświetlany jest następujący komunikat ostrzegawczy: „Certyfikaty podwójnego zastosowania dla co najmniej jednego towaru podwójnego zastosowania w tym zamówieniu sprzedaży są nieprawidłowe. Czy chcesz kontynuować, potwierdzająć tę informację?"

W tym temacie wyjaśniono, jak skonfigurować wszystkie ustawienia wymagane do skonfigurowania towarów podwójnego zastosowania i obsługi tego scenariusza.

## <a name="define-dual-use-requirements-for-each-relevant-country"></a>Zdefiniuj wymagania dotyczące podwójnego zastosowania dla każdego z właściwych krajów

Różne kraje mają różne wymagania dotyczące produktów podwójnego zastosowania. Strona **Konfiguracja kraju dla podwójnego zastosowania** umożliwia śledzenie krajów, które nie wymagają certyfikatu. Informacje, które tu określisz, są sprawdzane podczas tworzenia zamówień sprzedaży i zostanie wyświetlone przypomnienie o konieczności dostarczenia wymaganych certyfikatów.

Aby skonfigurować informacje o wymaganiach podwójnego zastosowania dla różnych krajów, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Zgodność produktu \> Produkty podwójnego zastosowania \> Konfiguracja kraju dla podwójnego zastosowania**.
2. Wybierz ustawienia istniejącego kraju, aby je edytować, lub wybierz opcję **Nowy** w Okienku akcji, aby utworzyć nowe ustawienia kraju.
3. Ustaw następujące wartości dla wybranej lub nowej konfiguracji kraju.

    | Pole | opis |
    |---|---|
    | Kraj/region | Umożliwia wybranie kraju, dla którego są śledzone wymagania. |
    | Wymagany certyfikat | Zaznacz to pole wyboru w przypadku krajów, w których wymagana jest certyfikacja towarów podwójnego zastosowania. Należy je wyczyścić w krajach, które nie wymagają tego certyfikatu. |

## <a name="create-dual-use-categories"></a>Utwórz kategorie podwójnego zastosowania

Towary podwójnego zastosowania muszą być często klasyfikowane zgodnie z ich numerem klasyfikacyjnym kontroli eksportu (ECCN). ECCN to kod alfanumeryczny, który klasyfikuje pozycje na podstawie takich czynników, jak towar i technologia. Strona **Kategorie podwójnego zastosowania** umożliwia utworzenie listy kategorii używanych do celów raportowania.

Aby skonfigurować kategorie podwójnego zastosowania, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Zgodność produktu \> Produkty podwójnego zastosowania \> Kategorie podwójnego zastosowania**.
2. Wybierz ustawienia kategorii, aby je edytować, lub wybierz opcję **Nowy** w Okienku akcji, aby utworzyć nową kategorię.
3. Ustaw następujące wartości dla wybranej lub nowej kategorii.

    | Pola | opis |
    |---|---|
    | Kod podwójnego zastosowania | Wprowadź pełny kod ECCN (np. *3A001*).|
    | Kategoria podwójnego zastosowania | Wprowadź część kodu ECCN dotyczącą kategorii listy kontroli handlu (CCL). Na przykład dla kodu ECCN *3A001* jest to wartość *3*. |
    | Grupa podwójnego zastosowania | Umożliwia wprowadzenie części grupy produktów w kodzie ECCN. Na przykład dla kodu ECCN *3A001* jest to wartość *A*. |
    | Tryb podwójnego zastosowania | Wprowadź kod trybu dla przedmiotu. Ten kod określa powód, dla którego produkt jest klasyfikowany jako towar podwójnego zastosowania. Na przykład dla kodu ECCN *3A001* jest to wartość *001*. |

## <a name="apply-dual-use-categories-to-products"></a>Stosowanie kategorii podwójnego zastosowania do produktów

Aby zidentyfikować produkt jako towar podwójnego zastosowania i zastosować do niego kategorię podwójnego zastosowania, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz lub utwórz produkt, aby otworzyć jego stronę **Szczegółów zwolnionego produktu**.
1. Na skróconej karcie **Handel zagraniczny** ustaw opcję **Produkty podwójnego zastosowania** na **Tak**, aby określić, że bieżący produkt jest stosowany w postaci podwójnego zastosowania.
1. W polu **Kod podwójnego zastosowania** określ kod, który ma zastosowanie do bieżącego produktu. (Kod ten został zdefiniowany na stronie **Kategorie podwójnego zastosowania**.)

Ta konfiguracja jest sprawdzana podczas tworzenia zamówienia sprzedaży.

## <a name="set-up-dual-use-certificates"></a>Konfigurowanie certyfikatów podwójnego zastosowania

Strona **Certyfikaty podwójnego zastosowania** umożliwia konfigurowanie wymaganych certyfikatów podwójnego zastosowania dla każdego produktu i kraju oraz zarządzanie nimi. Można śledzić szczegóły poszczególnych certyfikatów, takie jak kraj i daty ważności. Można również ustawić opcje określające miejsce drukowania tych informacji. Informacje mogą być na przykład drukowane na fakturze, dokumencie dostawy i/lub zamówieniu sprzedaży. Ta konfiguracja jest sprawdzana podczas tworzenia zamówienia sprzedaży.

1. Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Zgodność produktu \> Produkty podwójnego zastosowania \> Certyfikaty podwójnego zastosowania**.
2. Wybierz ustawienia certyfikatu, aby je edytować, lub wybierz opcję **Nowy** w Okienku akcji, aby utworzyć nowy certyfikat.
3. Ustaw następujące wartości dla wybranego lub nowego certyfikatu.

    | Pole | opis |
    |---|---|
    | Identyfikator pozycji | Wybierz numer pozycji podwójnego zastosowania, do której ma zastosowanie ten certyfikat. |
    | Kraj/region | Docelowy kraj lub region, w którym musisz skorzystać z tego certyfikatu. |
    | Numer certyfikacji | Numer wyświetlany na certyfikacie wystawionym dla dostawcy lub odbiorcy. |
    | Obowiązują | Umożliwia wybór pierwszej daty ważności bieżącego certyfikatu.|
    | Data ważności | Umożliwia wybór ostatniej daty ważności bieżącego certyfikatu. |
    | Drukowanie na fakturze | To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na fakturach, które są adresowane do określonego kraju w ciągu określonego zakresu dat. |
    | Drukowanie na dokumencie dostawy | To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na dokumencie dostawy, które są adresowane do określonego kraju w ciągu określonego zakresu dat. |
    | Drukowanie na zamówieniach sprzedaży | To pole wyboru należy zaznaczyć, aby wydrukować numer certyfikatu na zamówieniu sprzedaży, które są adresowane do określonego kraju w ciągu określonego zakresu dat. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
