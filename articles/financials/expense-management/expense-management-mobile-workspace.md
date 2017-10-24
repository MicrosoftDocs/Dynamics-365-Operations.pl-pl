---
title: "Mobilny obszar roboczy Zarządzanie wydatkami"
description: "Ten temat zawiera informacje o komórkowym obszarze roboczym Zarządzanie wydatkami. Ten obszar roboczy pozwala użytkownikom rejestrować i przekazywać paragony, dzięki czemu można je później dołączać do raportów z wydatków. Użytkownicy szybko utworzyć wiersz wydatku za pomocą dołączonego paragonu oraz tworzyć raporty z wydatków i nimi zarządzać."
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 7ce4c9d13a8686c82af8acad39d68858e52ba520
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="expense-management-mobile-workspace"></a>Mobilny obszar roboczy Zarządzanie wydatkami

[!include[banner](../includes/banner.md)]

Ten temat zawiera informacje o komórkowym obszarze roboczym **Zarządzanie wydatkami**. Ten obszar roboczy pozwala użytkownikom rejestrować i przekazywać paragony, dzięki czemu można je później dołączać do raportów z wydatków. Użytkownicy szybko utworzyć wiersz wydatku za pomocą dołączonego paragonu oraz tworzyć raporty z wydatków i nimi zarządzać. Osoby zatwierdzające mogą w mobilnym obszarze roboczym **Zarządzanie wydatkami** wyświetlać raporty z wydatków, które im przypisano, oraz zatwierdzać lub odrzucać te raporty.


Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji komórkowej Microsoft Dynamics 365 for Unified Operations.


## <a name="overview"></a>Przegląd

Wiele organizacji wymaga, aby kopie paragonów były dołączane do raportów o wydatkach z podróży lub wydatkach biznesowych, które pracownicy składają w celu uzyskania zwrotu pieniędzy. Mobilny obszar roboczy **Zarządzanie wydatkami** pozwala użytkownikom szybko tworzyć nowe wiersze wydatków na dowolnych urządzeniach komórkowych za pomocą dołączonej fotografii paragonu. Alternatywnie użytkownicy mogą zarejestrować zdjęcie paragonu i później dołączyć je do raportu z wydatków. Pracownicy mogą również na swoich urządzeniach komórkowych tworzyć wydatki z raportów i nimi zarządzać, a następnie przesyłać je do zatwierdzenia i zwrotu.


W szczególności mobilny obszar roboczy **Zarządzanie wydatkami** pozwala użytkownikom wykonywać następujące zadania:

- Wykonanie zdjęcia paragonu i przekazanie go do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Następnie można załączyć to zdjęcie do raportu z wydatków.
- Przekazanie pliku jako zarejestrowanego paragonu. Następnie można załączyć ten plik do raportu z wydatków.
- Utworzenie nowego wiersza wydatku za pomocą dołączonego paragonu. Można później dodać pozycję wiersza do raportu z wydatków i przesłać raport do zatwierdzenia w celu otrzymania zwrotu pieniędzy.

Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017 r.), masz dostęp również do następujących funkcji:

- Tworzenie nowego raportu z wydatków.
- Dołączanie transakcji kartami kredytowymi i innych utworzonych wcześniej wydatków do raportu z wydatków.
- Tworzenie nowych wydatków do raportu z wydatków.
- Dołączanie paragonu do dowolnego wydatku w raporcie z wydatków poprzez zrobienie zdjęcia paragonu lub przekazanie pliku jako zrzutu ekranu z paragonem.
- W zależności od firmowych zasad dotyczących wydatków w firmie — dodawanie listy gości do wydatku.
- W zależności od firmowych zasad dotyczących wydatków — wyszczególnianie pozycji wydatków.
- Przesyłanie raportu z wydatków do zatwierdzenia i zwrotu pieniędzy.
- Zatwierdzanie lub odrzucanie raportów z wydatków, dla których użytkownik jest przypisany jako osoba zatwierdzająca.

## <a name="prerequisites"></a>Wymagania wstępne
Wymagania wstępne różnią się w zależności od wersji programu Microsoft Dynamics 365 wdrożonej w organizacji.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017 r.) 
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (lipiec 2017 r.), administrator systemu musi opublikować mobilny obszar roboczy **Zarządzanie wydatkami**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą, administrator systemu musi wykonać następujące zadania wstępne. 

<table>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>Rola</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zainstalowanie poprawki KB 4019015.</td>
<td>Administrator systemu</td>
<td>KB 4019015 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Zarządzanie wydatkami</strong>. W celu zainstalowania poprawki KB 4019015 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Utwórz wdrażalny pakiet</a> zawierający modele <strong>ApplicationSuite</strong> i <strong>ExpenseMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Zastosuj wdrażalny pakiet</a></li>
</ol></td>
</tr>
<tr class="even">
<td>Opublikowanie mobilnego obszaru roboczego <strong>Zarządzanie wydatkami</strong>.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Pobieranie i instalowanie aplikacji komórkowej Dynamics 365 for Operations
Pobierz i zainstaluj aplikację komórkową Dynamics 365 for Unified Operations:

- [Telefony z systemem Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej
1. Uruchom aplikację na urządzeniu komórkowym.
2. Wprowadź adres URL usługi Dynamics 365.
4. Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
5. Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.


[![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Rejestrowanie paragonu za pomocą komórkowego obszaru roboczego Zarządzanie wydatkami

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie wydatkami**.
2. Wybierz opcję **Zarejestruj paragon**.
3. Wybierz opcję **Zrób zdjęcie** lub **Wybierz obraz**.
4. Wykonaj jeden z następujących kroków:

    - Jeśli wybrano opcję **Zrób zdjęcie**, wykonaj następujące kroki:

        1. Uruchamiasz aparat w swoim urządzeniu komórkowym, aby można było sfotografować paragon. Po zakończeniu robienia zdjęcia kliknij przycisk **OK**, aby zaakceptować zdjęcie.
        2. Opcjonalnie: Nadaj fotografii nazwę i ewentualnie wprowadź notatki.

    - W przypadku wybrania opcji **Wybierz obraz** wykonaj następujące kroki:

        1. Wybierz zdjęcie z listy.
        2. Opcjonalnie: Nadaj zdjęciu nazwę i ewentualnie wprowadź notatki.

5. Wybierz opcję **Gotowe**.

## <a name="quickly-enter-expenses-by-using-the-expense-management-mobile-workspace"></a>Szybkie wprowadzanie wydatków za pomocą komórkowego obszaru roboczego Zarządzanie wydatkami
1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie wydatkami**.
2. Wybierz opcję **Szybkie wprowadzanie wydatku**.
3. Wybierz kategorię wydatku. Zobaczysz listę kategorii wydatków załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Jeśli Twojej kategorii nie ma na liście, kliknij przycisk **Szukaj**, aby przeprowadzić wyszukiwanie online. Poszukaj według kategorii wydatków lub przejdź do wyszukiwania według typu wydatku.
4. Wprowadź datę transakcji wydatkowej.
5. Opcjonalnie: Wprowadź handlowca dla wydatku.
6. Wprowadź kwotę wydatku.
7. Wybierz walutę wydatku. Zobaczysz listę kodów walut załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 400 walut, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Jeśli Twojej waluty nie ma na liście, kliknij przycisk **Szukaj**, aby przeprowadzić wyszukiwanie online. Wyszukaj według waluty lub przełącz się do wyszukiwania według nazwy.
8. Wybierz opcję **Zrób zdjęcie** lub **Wybierz obraz**.
9. Wykonaj jeden z następujących kroków:

    - Jeśli wybrano opcję **Zrób zdjęcie**, zostanie uruchomiony aparat w swoim urządzeniu komórkowym, aby można było sfotografować paragon. Po zakończeniu robienia zdjęcia kliknij przycisk **OK**, aby zaakceptować zdjęcie.
    - W przypadku wybrania opcji **Wybierz obraz** wybierz obraz z listy.

10. Wybierz opcję **Gotowe**.

## <a name="approve-an-expense-report-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Zatwierdzanie raportu z wydatków za pomocą komórkowego obszaru roboczego Zarządzanie wydatkami (jeśli używasz aktualizacji z lipca 2017 r.)
1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie wydatkami**.
2. Obszar **Zatwierdzenia wydatków** pokazuje liczbę raportów z wydatków przypisanych Ci do zatwierdzenia. Ta liczba jest aktualizowana co około 30 minut. Wybierz opcję **Zatwierdzenia wydatków**.

    Zostanie wyświetlona liczba raportów z wydatków przypisanych Ci do zatwierdzenia.
    
3. Wybierz raport wydatków, aby wyświetlić szczegóły zawartych w nim wydatków.
4. Wybierz wydatek, aby wyświetlić jego szczegóły. Informacje wyświetlane dla wydatku obejmują wszystkie szczegóły paragonu, gości i pozycji wydatkowych.
5. Z powrotem na stronie **Raport o wydatkach** wybierz opcję zatwierdzenia lub odrzucenia raportu z wydatków.
6. Wprowadź wszelkie komentarze dotyczące czynności zatwierdzania.
7. Wybierz opcję **Gotowe**.

## <a name="create-a-new-expense-report-and-submit-it-for-approval-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Tworzenie nowego raportu z wydatków i przesyłanie go do zatwierdzenia za pomocą komórkowego obszaru roboczego Zarządzanie wydatkami (jeśli używasz aktualizacji z lipca 2017 r.)
1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie wydatkami**.
2. Wybierz opcję **Wpis wydatku**.
3. Wybierz opcję **Nowy raport** lub zaznacz istniejący raport z wydatków na liście.
4. Dla nowego raportu z wydatków wprowadź cel oraz wszelkie dodatkowe informacje, które są dostępne. Te informacje różnią się w zależności od konfiguracji modułu Zarządzanie wydatkami w firmie.
5. Wybierz opcję **Gotowe**.
6. Aby do raportu z wydatków dodać istniejące wydatki, takie jak transakcje kartami kredytowymi, wybierz opcję **Dołącz**.
7. Zaznacz jeden lub więcej wydatków na liście.
8. Wybierz opcję **Gotowe**.
9. Aby dodać nowy wydatek do raportu z wydatków, wybierz opcję **Nowy wydatek**.
10. Wybierz kategorię wydatku. Zobaczysz listę kategorii wydatków załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Jeśli Twojej kategorii nie ma na liście, kliknij przycisk **Szukaj**, aby przeprowadzić wyszukiwanie online. Poszukaj według kategorii wydatków lub przejdź do wyszukiwania według typu wydatku.
11. Opcjonalnie: Wprowadź handlowca dla wydatku.
12. Wprowadź datę transakcji wydatkowej.
13. Wprowadź kwotę wydatku.
14. Wybierz walutę wydatku. Zobaczysz listę kodów walut załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 400 walut, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Jeśli Twojej waluty nie ma na liście, kliknij przycisk **Szukaj**, aby przeprowadzić wyszukiwanie online. Wyszukaj według waluty lub przełącz się do wyszukiwania według nazwy.
15. Wybierz opcję **Gotowe**.
16. Aby dodać więcej szczegółów do wydatku, wybierz opcję **Dodaj więcej szczegółów**. Dostępne pola zależą od konfiguracji modułu Zarządzanie wydatkami w firmie.
17. Jeśli zasady obowiązujące w firmie wymagają wskazania paragonu dla wydatku, wybierz opcję **Paragony**, a następnie wykonaj poniższe czynności:

    1. Wybierz opcję **Przechwyć paragon** lub **Dołącz paragon**.
    2. Wykonaj jeden z następujących kroków:

        - W przypadku wybrania opcji **Przechwyć paragon** wykonaj następujące kroki:

            1. Wybierz opcję **Zrób zdjęcie** lub **Wybierz obraz**.
            2. Wykonaj jeden z następujących kroków:

                - Jeśli wybrano opcję **Zrób zdjęcie**, wykonaj następujące kroki:

                    1. Uruchamiasz aparat w swoim urządzeniu komórkowym, aby można było sfotografować paragon. Po zakończeniu robienia zdjęcia kliknij przycisk **OK**, aby zaakceptować zdjęcie.
                    2. Opcjonalnie: Nadaj fotografii nazwę i ewentualnie wprowadź notatki.

                - W przypadku wybrania opcji **Wybierz obraz** wykonaj następujące kroki:

                    1. Wybierz zdjęcie z listy.
                    2. Opcjonalnie: Nadaj zdjęciu nazwę i ewentualnie wprowadź notatki.

            3.  Wybierz opcję **Gotowe**.

        - W przypadku wybrania opcji **Dołącz paragon** wykonaj następujące kroki:

            1.  Zaznacz jeden lub więcej obrazów na liście.
            2.  Wybierz opcję **Gotowe**.

    3. Kliknij przycisk **Wstecz**, aby wrócić do szczegółów wydatku.

18. Jeśli zasady obowiązujące w firmie wymagają wskazania gości dla wydatku, wybierz opcję **Goście**, a następnie wykonaj poniższe czynności:

    1. Wybierz opcję **Gość**, **Poprzedni goście** lub **Współpracownicy**.
    2. Wykonaj jeden z następujących kroków:

        - Jeśli wybrano opcję **Gość**, wykonaj następujące kroki:

            1. Wprowadź imię i nazwisko gościa.
            2. Opcjonalnie: Wprowadź organizację i/lub kraj gościa.
            3. Opcjonalnie: Wprowadź tytuł gościa.
            4. Wybierz opcję **Gotowe**.

        - W przypadku wybrania opcji **Poprzedni goście** wykonaj następujące kroki:

            1. Zaznacz jednego lub więcej poprzednich gości na liście. Zobaczysz listę poprzednich gości dodanych do poprzednich raportów z wydatków, które są załadowane do aplikacji do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Jeśli Twojego poprzedniego gościa nie ma na liście, kliknij przycisk **Szukaj**, aby przeprowadzić wyszukiwanie online. Poszukaj według nazwy lub przejdź do wyszukiwania według organizacji, kraju albo tytułu.
            2. Wybierz opcję **Gotowe**.

        - Jeśli wybrano opcję **Współpracownicy**, wykonaj następujące kroki:

            1. Zaznacz jednego lub więcej współpracowników na liście. Zobaczysz listę współpracowników załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Jeśli Twojego współpracownika nie ma na liście, kliknij przycisk **Szukaj**, aby przeprowadzić wyszukiwanie online. Poszukaj według nazwy lub przejdź do wyszukiwania według firmy albo tytułu.
            2. Wybierz opcję **Gotowe**.

    3. Kliknij przycisk **Wstecz**, aby wrócić do szczegółów wydatku.

19. Jeśli zasady obowiązujące w firmie wymagają wyszczególnienia pozycji wydatku, wybierz opcję **Podziel na pozycje**, a następnie wykonaj poniższe czynności:

    1. Zaznacz pierwszą datę, dla której chcesz wyszczególnić pozycje wydatkowe.
    2. Wybierz opcję **Dodaj podział na pozycje**.
    3. Wybierz podkategorię wyszczególnienia pozycji wydatku. Zobaczysz listę podkategorii wydatków załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma mobilna](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Jeśli Twojej podkategorii nie ma na liście, kliknij przycisk **Szukaj**, aby przeprowadzić wyszukiwanie online. Poszukaj według nazwy podkategorii wydatków.
    4. Wprowadź kwotę transakcji dla wyszczególnienia.
    5. W razie potrzeby edytuj datę transakcji.
    6. Wybierz opcję **Gotowe**.
    7. Powtarzaj powyższe czynności, aż dodasz wszystkie wyszczególnienia dla wybranej daty.
    8. Dla kolejnych dni możesz wybrać opcję **Kopiuj do następnego dnia** i skopiować wyszczególnienia do następnego dnia. Alternatywnie możesz wybrać datę do wyszczególnienia, a następnie dodać wyszczególnienia tak samo, jak dla pierwszej daty.
    9. Po zakończeniu wyszczególniania wydatku kliknij przycisk **Wstecz**, aby wrócić do szczegółów wydatku.

20. Kliknij przycisk **Wstecz**, aby wrócić do strony **Raport o wydatkach**.
21. Powtarzaj powyższe czynności, aż dodasz wszystkie wydatki.
22. Wybierz opcję **Prześlij**.
23. Wprowadź wszelkie komentarze dla osoby zatwierdzającej.
24. Wybierz opcję **Gotowe**.

