---
title: Konfigurowanie kont odbiorców
description: W tym temacie opisano typy informacji, które należy wprowadzić podczas tworzenia nowego konta dostawcy.
author: kamaybac
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: smmContactPerson, VendBankAccounts, VendTable, VendOnHoldUpdate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 191053
ms.assetid: 06168199-7c54-40e9-a038-4eb274ca958d
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 587555f5d2631d09175fec67d3707b2aa9e7919d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812477"
---
# <a name="set-up-vendor-accounts"></a>Konfigurowanie kont odbiorców

[!include [banner](../includes/banner.md)]

W tym temacie opisano typy informacji, które należy wprowadzić podczas tworzenia nowego konta dostawcy.

Podczas tworzenia konta dostawcy wprowadza się informacje o dostawcy. Te informacje są używane do automatycznego wprowadzania danych w dokumentach oraz do śledzenia działań dotyczących dostawcy. Na przykład można skonfigurować następujące informacje dotyczące dostawcy:

-   Przypisz grupę dostawców. Każdy dostawca musi być przypisany do grupy dostawców. Dostawcy w grupie dostawców mają parametry, które są przez nich współużytkowane. Na przykład mogą mieć te same warunki płatności.
-   Skonfiguruj dostawcę dla importu katalogu. Dostawca może dostarczyć plik zawierający katalog jego towarów i usług. Ten plik można przekazać na serwer, co pozwoli pracownikom zamawiać od dostawcy.
-   Przypisz kategorie zaopatrzenia do dostawcy.
-   Zezwalaj istniejącemu dostawcy robić interesy z inną firmą w organizacji.
-   Wstrzymaj dostawcę dla określonych typów transakcji.
-   Skonfiguruj informacje bankowe dla dostawcy, dzięki czemu będzie można wysyłać płatności drogą elektroniczną.
-   Skonfiguruj podatek, dostawę, fakturę i informacje o płatności dla dostawcy. Domyślnie te ustawienia są kopiowane do nowych dokumentów, które tworzysz dla dostawcy.
-   Ustaw domyślne wymiary finansowe, które są używane do automatycznego księgowania transakcji z dostawcą na kontach finansowych.

Aby przyspieszyć proces tworzenia kont dostawców, można utworzyć szablony. Aby utworzyć szablon, na stronie **Dostawca** w okienku akcji kliknij kolejno pozycje **Opcje** &gt; **Informacje o rekordzie**. Następnie kliknij opcję **Szablon firmy**. Szablony kont firmowych są udostępniane innym użytkownikom.  

Można także utworzyć szablon użytkownika do własnego użytku. Nie można usunąć dostawcy, który jest skojarzony z innymi rekordami, np. kontaktów lub produktów.

## <a name="vendor-account-numbers"></a>Numery kont dostawców
Numer konta jest unikatowym identyfikatorem dostawcy. Można ustawić automatyczne generowanie numerów kont przy tworzeniu dostawców. Można także skonfigurować numerację w celu ręcznego wprowadzania numerów kont. Na przykład można użyć numeru telefonu dostawcy jako identyfikatora.

## <a name="vendor-organizations-and-individual-vendors"></a>Organizacje dostawców i indywidualni dostawcy
Podczas tworzenia nowego konta dostawcy należy wybrać, czy dostawca jest organizacją, czy osobą. Wybór wpływa na informacje, które należy wypełnić dla dostawcy. W wypadku osoby jest to imię, nazwisko i tytuł. Dla organizacji informacje te obejmują numer organizacji i liczbę pracowników.

## <a name="addresses"></a>Adresy
Dla każdego dostawcy można określić wiele adresów, z których każdy będzie używany do innego celu. Można na przykład utworzyć adres, który ma cel **Faktura**. Albo jeśli będziesz płacić dostawcy czekami, można utworzyć adres o celu **Przekaż do**. Jeśli trzeba określić adres, który będzie używany dla przekazów pieniężnych do banków zagranicznych, celem będzie **SWIFT**.

## <a name="vendor-contacts"></a>Osoby kontaktowe dostawców
Można przechowywać dane osób kontaktowych dostawców. Te kontakty mogą być następnie używane w dokumentach takich jak zamówienia zakupu lub zapytania ofertowe (ZO).  

Aby dodać osoby kontaktowe dla dostawcy, na stronie **Wszyscy dostawcy** na karcie **Dostawca** w grupie **Konfiguracja** kliknij kolejno opcje **Kontakty** &gt; **Dodaj kontakty**.  

Kontakty dostawców można tworzyć od podstaw. Alternatywnie można skopiować szczegóły z innej osoby, która jest już zarejestrowana w Supply Chain Management, i edytować informacje w żądany sposób.  

**Uwaga:** Dodanie kontaktu dla dostawcy nie jest tym samym, co dodanie informacji kontaktowych dla tego dostawcy. Chociaż można dodać ogólne informacje kontaktowe dostawcy, można również wyznaczyć kilka określonych osób będących kontaktami w tej firmie i wszystkie te osoby mają własne informacje kontaktowe.  

Nie można usunąć rekordu osoby kontaktowej, jeżeli istnieje odwołanie do niej w dokumencie. Zamiast tego można zdezaktywować kontakt.  

Osoby kontaktowe dostawcy można dodać do kontaktów osobistych w usłudze Microsoft 365. Jednakże najpierw należy skonfigurować synchronizację między Supply Chain Management a usługą Microsoft 365 w ustawieniach synchronizacji Microsoft Exchange Server oraz w kreatorze instalacji Microsoft Outlook.

## <a name="vendors-in-different-legal-entities"></a>Dostawcy w różnych firmach
Jeśli dostawca jest zarejestrowany tylko dla jednej firmy w organizacji, a inne firmy muszą zarejestrować tego samego dostawcę, można użyć strony **Dodawanie dostawcy do innej firmy**, aby skonfigurować dostawcę do współpracy z inną firmą. Należy wybrać grupę dostawców, walutę i stan wstrzymania dla dostawcy w wybranej firmie.  

Jeśli kilka firm w ramach jednej organizacji prowadzi interesy z tym samym dostawcą i każda z nich prowadzi oddzielne konto dla tego dostawcy, można scalić identyfikatory stron odnoszące się do kont dostawcy. W ten sposób można udostępnić informacje takie jak adres i liczba pracowników, co pozwoli je aktualizować tylko w jednym miejscu.  

Aby scalić identyfikatory stron, wykonaj następujące kroki.

1.  Na stronie **Globalna książka adresowa** zaznacz rekordy książki adresowej odpowiadające dostawcy w każdej firmie, która powinna zostać uwzględniona w mapowaniu.
2.  W okienku akcji kliknij opcję **Scal rekordy**.

## <a name="agreements"></a>Umowy
Po skonfigurowaniu konta dostawcy można zarejestrować umowy zawarte z dostawcą. Korzystając z akcji w rekordzie dostawcy, można skonfigurować umowy handlowe. Można także skonfigurować umowę zakupu na stronie **Umowy zakupu**.

## <a name="putting-a-vendor-on-hold"></a>Wstrzymywanie dostawcy
Można wstrzymywać dostawcę dla różnych typów transakcji. Dostępne są następujące opcje:

-   **Nie** — Nie nałożono żadnych wstrzymań dla dostawcy.
-   **Faktura** — Nie można księgować żadnych faktur dla dostawcy.
-   **Wszystko** — Dostawca jest wstrzymany dla wszystkich typów transakcji. Obejmuje to transakcje zapotrzebowań na zakup, faktur i płatności.
-   **Płatność** — Nie można wygenerować żadnych płatności dla dostawcy.
-   **Zapotrzebowanie** — zapotrzebowania na zakup nie można utworzyć dla dostawcy, a wiersze zapotrzebowania zostały już utworzone, zanim dostawca został określony jako wstrzymany, nie można przetworzyć na zamówienie zakupu. Wiersze zapotrzebowania dla dostawcy zostaną anulowane, jeśli w zasadach ustawiono Automatyczne tworzenie zamówień zakupu.
-   **Nigdy** — Na dostawcę nigdy nie są nakładane wstrzymania działań.

Gdy wstrzymujesz dostawcę, można także określić przyczynę wstrzymania oraz datę końcową stanu wstrzymania. Jeśli nie wprowadzisz daty końcowej, stan wstrzymania dostawcy trwa przez czas nieokreślony.

Można zbiorczo zaktualizować stan wstrzymania na **Wszystko** dla dostawców na podstawie kryteriów wybranych na stronie **Zdezaktywowanie dostawcy** oraz przypisać przyczynę wstrzymania dostawcy.

Następujące kryteria są używane do uwzględnienia dostawców, którzy byli nieaktywni w okresie, uwzględnienia lub wykluczenia dostawców, którzy są pracownikami, oraz wykluczenia dostawców, którzy znajdują się w okresie prolongaty przed następnym wstrzymaniem.

- Na podstawie liczby dni wprowadzonej w polu **W okresie działania** na stronie **Zdezaktywowanie dostawcy** aplikacja oblicza ostatni dzień, kiedy dostawca może wykonać działanie, zanim zostanie uznany za nieaktywnego. Dokładnie rzecz biorąc, od bieżącego dnia jest odejmowana wpisana liczba dni. Jeśli istnieje co najmniej jedna faktura od dostawcy, której data jest późniejsza niż obliczona najpóźniejsza data, dostawca zostanie wykluczony z dezaktywacji. Jest to również weryfikowane, gdy dostawca ma płatności po tej dacie, otwarte zapotrzebowania na zakup, otwarte zamówienia zakupu, zapytania ofertowe lub odpowiedzi.
- Liczba dni w polu **Czas prolongaty przed następnym wstrzymaniem** jest używana do obliczania najpóźniejszej daty okresu prolongaty. Dokładnie rzecz biorąc, od bieżącego dnia jest odejmowana wpisana liczba dni. Dotyczy to tylko dostawców, którzy wcześniej zostali zdezaktywowani. W przypadku wcześniejszej dezaktywacji aplikacja weryfikuje historię pozostałych wystąpień dezaktywacji dostawcy i sprawdza, czy ostatnia dezaktywacja nastąpiła przed najpóźniejszą datą okresu prolongaty. Jeśli tak istotnie było, dostawca zostanie uwzględniony w procesie dezaktywacji.
- Parametr **Uwzględnij pracowników etatowych** odnosi się do dostawców przypisanych do pracownika. Możesz określić, czy chcesz uwzględniać tych pracowników.

Ten proces zawsze powoduje wyłączenie dostawców, którzy w ustawieniu **Wstrzymanie dostawcy** mają wartość **Nigdy**.

Dostawcy pomyślnie przechodzący weryfikację są wstrzymywani, co powoduje ustawienie w polu **Wstrzymanie dostawcy** wartości **Wszystko**, a w polu **Przyczyna** wybranego powodu. Dla dostawcy jest tworzony rekord w historii wstrzymań.

## <a name="vendor-invoice-account"></a>Konto płatnika dostawcy
Jeśli istnieje więcej niż jeden dostawca z takim samym adresem rozliczeniowym lub jeśli dostawca jest fakturowany przez firmę zewnętrzną, można określić konto płatnika w rekordzie dostawcy. Konto płatnika jest kontem, na którym po stronie kredytowej księgowana jest kwota faktury przy tworzeniu faktury od dostawcy z zamówienia zakupu. Jeśli nie zostanie wprowadzone konto płatnika w rekordzie dostawcy, jego funkcję będzie spełniać konto dostawcy.

## <a name="vendor-bank-accounts"></a>Konta bankowe dostawcy
Jeśli trzeba dokonywać płatności na konto bankowe dostawcy, można wprowadzić informacje dotyczące banku i kont bankowych dostawcy na stronie **Konta bankowe dostawcy**. Można również wprowadzić informacje na temat sprawdzania poprawności i płatności dla konta bankowego. Na przykład można dodać przelewy testowe do kont bankowych dostawcy. Te przelewy testowe mogą służyć do weryfikacji dokładności danych księgowych, takich jak numery rozliczeniowe i numery kont. Należy określić domyślne konto dla płatności na rzecz dostawcy. Jednak podczas faktycznego dokonywania płatności można zmienić to konto na jedno z innych kont dostawcy.

## <a name="ledger-accounts"></a>Konta księgowe
Można określić konta domyślne, które będą automatycznie wyświetlane w arkuszach faktur od wybranego dostawcy. Ta funkcja może być przydatna, jeśli zwykle płacisz za te same typy towarów lub usług od tych samych dostawców przez dłuższy czas. Po określeniu domyślnego konta można szybko i sprawnie dokonywać wpisów w arkuszu faktur. Ustawione domyślne konta nie są używane do zamówień zakupu ani do faktur od dostawcy wprowadzonych na stronie **Faktura od dostawcy**.  

Domyślne konta wybiera się na stronie **Ustawienia konta domyślnego**, którą można otworzyć za pomocą karty **Faktura** w rekordzie dostawcy. Konta wybrane w tym miejscu są wyświetlane na wyfiltrowanej liście kont dostawcy podczas wprowadzania wpisu w arkuszu. Można ustawić jedno z kont jako konto domyślne.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]