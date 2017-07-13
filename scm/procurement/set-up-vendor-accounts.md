---
title: "Konfigurowanie kont odbiorców"
description: "W tym temacie opisano typy informacji, które należy wprowadzić podczas tworzenia nowego konta dostawcy."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: smmContactPerson, VendBankAccounts, VendTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 191053
ms.assetid: 06168199-7c54-40e9-a038-4eb274ca958d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 4c97f11fa85b8eee54daea8ccaa183859a89fe7f
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Konfigurowanie kont odbiorców
<a id="set-up-vendor-accounts" class="xliff"></a>

[!include[banner](../includes/banner.md)]


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

## Numery kont dostawców
<a id="vendor-account-numbers" class="xliff"></a>
Numer konta jest unikatowym identyfikatorem dostawcy. Można ustawić automatyczne generowanie numerów kont przy tworzeniu dostawców. Można także skonfigurować numerację w celu ręcznego wprowadzania numerów kont. Na przykład można użyć numeru telefonu dostawcy jako identyfikatora.

## Organizacje dostawców i indywidualni dostawcy
<a id="vendor-organizations-and-individual-vendors" class="xliff"></a>
Podczas tworzenia nowego konta dostawcy należy wybrać, czy dostawca jest organizacją, czy osobą. Wybór wpływa na informacje, które należy wypełnić dla dostawcy. W wypadku osoby jest to imię, nazwisko i tytuł. Dla organizacji informacje te obejmują numer organizacji i liczbę pracowników.

## Adresy
<a id="addresses" class="xliff"></a>
Dla każdego dostawcy można określić wiele adresów, z których każdy będzie używany do innego celu. Można na przykład utworzyć adres, który ma cel **Faktura**. Albo jeśli będziesz płacić dostawcy czekami, można utworzyć adres o celu **Przekaż do**. Jeśli trzeba określić adres, który będzie używany dla przekazów pieniężnych do banków zagranicznych, celem będzie **SWIFT**.

## Osoby kontaktowe dostawców
<a id="vendor-contacts" class="xliff"></a>
Można przechowywać dane osób kontaktowych dostawców. Te kontakty mogą być następnie używane w dokumentach takich jak zamówienia zakupu lub zapytania ofertowe (ZO).  

Aby dodać osoby kontaktowe dla dostawcy, na stronie **Wszyscy dostawcy** na karcie **Dostawca** w grupie **Konfiguracja** kliknij kolejno opcje **Kontakty** &gt; **Dodaj kontakty**.  

Kontakty dostawców można tworzyć od podstaw. Alternatywnie można skopiować szczegóły z innej osoby, która jest już zarejestrowana w programie Microsoft Dynamics 365 for Finance and Operations, i zmodyfikować informacje w żądany sposób.  

**Uwaga:** Dodanie kontaktu dla dostawcy nie jest tym samym, co dodanie informacji kontaktowych dla tego dostawcy. Chociaż można dodać ogólne informacje kontaktowe dostawcy, można również wyznaczyć kilka określonych osób będących kontaktami w tej firmie i wszystkie te osoby mają własne informacje kontaktowe.  

Nie można usunąć rekordu osoby kontaktowej, jeżeli istnieje odwołanie do niej w dokumencie. Zamiast tego można zdezaktywować kontakt.  

Osoby kontaktowe dostawcy można dodać do kontaktów osobistych w usłudze Microsoft Office 365. Jednakże najpierw należy skonfigurować synchronizację między programem Finance and Operations a usługą Office 365 w ustawieniach synchronizacji programu Microsoft Exchange Server oraz w kreatorze instalacji programu Microsoft Outlook.

## Dostawcy w różnych firmach
<a id="vendors-in-different-legal-entities" class="xliff"></a>
Jeśli dostawca jest zarejestrowany tylko dla jednej firmy w organizacji, a inne firmy muszą zarejestrować tego samego dostawcę, można użyć strony **Dodawanie dostawcy do innej firmy**, aby skonfigurować dostawcę do współpracy z inną firmą. Należy wybrać grupę dostawców, walutę i stan wstrzymania dla dostawcy w wybranej firmie.  

Jeśli kilka firm w ramach jednej organizacji prowadzi interesy z tym samym dostawcą i każda z nich prowadzi oddzielne konto dla tego dostawcy, można scalić identyfikatory stron odnoszące się do kont dostawcy. W ten sposób można udostępnić informacje takie jak adres i liczba pracowników, co pozwoli je aktualizować tylko w jednym miejscu.  

Aby scalić identyfikatory stron, wykonaj następujące kroki.

1.  Na stronie **Globalna książka adresowa** zaznacz rekordy książki adresowej odpowiadające dostawcy w każdej firmie, która powinna zostać uwzględniona w mapowaniu.
2.  W okienku akcji kliknij opcję **Scal rekordy**.

## Umowy
<a id="agreements" class="xliff"></a>
Po skonfigurowaniu konta dostawcy można zarejestrować umowy zawarte z dostawcą. Korzystając z akcji w rekordzie dostawcy, można skonfigurować umowy handlowe. Można także skonfigurować umowę zakupu na stronie **Umowy zakupu**.

## Wstrzymywanie dostawcy
<a id="putting-a-vendor-on-hold" class="xliff"></a>
Można wstrzymywać dostawcę dla różnych typów transakcji. Dostępne są następujące opcje:

-   **Nie** — Nie nałożono żadnych wstrzymań dla dostawcy.
-   **Faktura** — Nie można księgować żadnych faktur dla dostawcy.
-   **Wszystko** — Dostawca jest wstrzymany dla wszystkich typów transakcji. Obejmuje to transakcje zapotrzebowań na zakup, faktur i płatności.
-   **Płatność** — Nie można wygenerować żadnych płatności dla dostawcy.
-   **Zapotrzebowanie** — Można tworzyć tylko zapotrzebowania na zakup. Nie będą tworzone żadne inne transakcje.
-   **Nigdy** — Na dostawcę nigdy nie są nakładane wstrzymania działań.

Gdy wstrzymujesz dostawcę, można także określić przyczynę wstrzymania oraz datę końcową stanu wstrzymania. Jeśli nie wprowadzisz daty końcowej, stan wstrzymania dostawcy trwa przez czas nieokreślony.

## Konto płatnika dostawcy
<a id="vendor-invoice-account" class="xliff"></a>
Jeśli istnieje więcej niż jeden dostawca z takim samym adresem rozliczeniowym lub jeśli dostawca jest fakturowany przez firmę zewnętrzną, można określić konto płatnika w rekordzie dostawcy. Konto płatnika jest kontem, na którym po stronie kredytowej księgowana jest kwota faktury przy tworzeniu faktury od dostawcy z zamówienia zakupu. Jeśli nie zostanie wprowadzone konto płatnika w rekordzie dostawcy, jego funkcję będzie spełniać konto dostawcy.

## Konta bankowe dostawcy
<a id="vendor-bank-accounts" class="xliff"></a>
Jeśli trzeba dokonywać płatności na konto bankowe dostawcy, można wprowadzić informacje dotyczące banku i kont bankowych dostawcy na stronie **Konta bankowe dostawcy**. Można również wprowadzić informacje na temat sprawdzania poprawności i płatności dla konta bankowego. Na przykład można dodać przelewy testowe do kont bankowych dostawcy. Te przelewy testowe mogą służyć do weryfikacji dokładności danych księgowych, takich jak numery rozliczeniowe i numery kont. Należy określić domyślne konto dla płatności na rzecz dostawcy. Jednak podczas faktycznego dokonywania płatności można zmienić to konto na jedno z innych kont dostawcy.

## Konta księgowe
<a id="ledger-accounts" class="xliff"></a>
Można określić konta domyślne, które będą automatycznie wyświetlane w arkuszach faktur od wybranego dostawcy. Ta funkcja może być przydatna, jeśli zwykle płacisz za te same typy towarów lub usług od tych samych dostawców przez dłuższy czas. Po określeniu domyślnego konta można szybko i sprawnie dokonywać wpisów w arkuszu faktur. Ustawione domyślne konta nie są używane do zamówień zakupu ani do faktur od dostawcy wprowadzonych na stronie **Faktura od dostawcy**.  

Domyślne konta wybiera się na stronie **Ustawienia konta domyślnego**, którą można otworzyć za pomocą karty **Faktura** w rekordzie dostawcy. Konta wybrane w tym miejscu są wyświetlane na wyfiltrowanej liście kont dostawcy podczas wprowadzania wpisu w arkuszu. Można ustawić jedno z kont jako konto domyślne.




