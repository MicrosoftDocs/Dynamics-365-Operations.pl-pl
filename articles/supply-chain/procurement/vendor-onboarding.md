---
title: Wdrażanie dostawców
description: W tym temacie opisano sposób wdrażania nowych dostawców. Wyjaśniono działania wymagane przez różne role w trakcie tego procesu.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, SysUserRequestListPage, VendRequestListPage, VendRequestCompanyProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 171d3b57333cc325fa675627e4c38f764d89f32c
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018659"
---
# <a name="onboard-vendors"></a>Wdrażanie dostawców

[!include [banner](../includes/banner.md)]

---

Nowych dostawców można wdrożyć i zarejestrować jako dostawców w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management na podstawie informacji zebranych od przedstawiciela dostawcy.

Ten proces składa się z następujących kroków, w których różne role wykonują określone akcje w systemie.

1. **Zarządzanie danymi OData** — Import jednostek — pierwszy wniosek dotyczy rejestracji potencjalnego dostawcy. Zwykle ten wniosek pochodzi ze źródła takiego jak witryny internetowej obsługiwanej przez klienta, która umożliwia anonimowy dostęp. Dostawcy mogą rejestrować się, podając podstawowe informacje, takie jak nazwa dostawcy, uzasadnienie, numer organizacji, a także imię i nazwisko oraz adres e-mail osoby kontaktowej. Wnioski są importowane za pomocą interfejsu Zarządzanie danymi.
2. **Strona listy wniosku o rejestrację potencjalnego dostawcy** — na podstawie informacji podanych we wniosku o rejestrację potencjalnego dostawcy pracownik działu zaopatrzenia określa, czy należy wdrożyć dostawcę. Pracownik działu zaopatrzenia wyświetla przychodzące wnioski na stronie listy **Wnioski o rejestrację potencjalnego dostawcy**.
3. **Przepływ pracy przypisywania użytkowników** — gdy pracownik działu zaopatrzenia sprawdzi informacje w otrzymanym wniosku i zdecyduje o kontynuacji procesu wdrażania, przepływ pracy dla wniosku użytkownika przypisuje nowego użytkownika, a następnie wysyła wiadomość e-mail z zaproszeniem w celu zaakceptowania osoby kontaktowej jako uwierzytelnionego użytkownika usługi Microsoft Dynamics 365.
4. **Kreator rejestracji dostawcy** — osoba kontaktowa dostawcy loguje się używając nowego konta użytkownika. Użytkownik wykonuje czynności w kreatorze rejestracji dostawcy w celu podania informacji takich jak adresy, informacje o firmie, kategorie zaopatrzenia i odpowiedzi w kwestionariuszu.
5. **Przepływ pracy zatwierdzania** — tworzony jest wniosek o nowego dostawcę zawierający informacje o rejestracji. Ten wniosek o nowego dostawcę jest przesyłany do przepływu pracy i rozsyłany w celu sprawdzenia i zatwierdzenia.
6. **Tworzenie danych głównych dostawcy i modyfikacja roli użytkownika** — po zatwierdzeniu wniosku o nowego dostawcę tworzony jest rekord dostawcy. Konto użytkownika osoby kontaktowej dostawcy uzyskuje uprawnienia do współpracy z dostawca lub jest dezaktywowane.

W poniższej tabeli przedstawiono kroki i role, które są zawarte w tym procesie.

| Rola i „proces”       | Zarządzanie danymi OData — import jednostki | Strona listy wniosków o rejestrację potencjalnych dostawców | Przepływ pracy przypisywania użytkowników | Kreator rejestracji dostawcy | Przepływ pracy zatwierdzania | Tworzenie danych głównych dostawcy i modyfikacja roli użytkownika |
|--------------------------|---|---|---|---|---|---|
| System                   | Wniosek o nowego dostawcę jest importowany. | | | | | Po zaakceptowaniu wniosku o nowego dostawcę tworzony jest rekord dostawcy. |
| Pracownik działu zaopatrzenia | | Uruchamia proces wdrażania. | | | Przegląda i akceptuje lub odrzuca wniosek o nowego dostawcę. | |
| Administrator            | | | Utwórz użytkownika w Supply Chain Management i Microsoft Azure. | | | |
| Osoba kontaktowa ze strony dostawcy    | | | Wysyła wiadomość e-mail do osoby kontaktowej. | Rejestruje informacje o dostawcy. | | |

Aby zapoznać się szybką demonstracją procesu przygotowywania dostawcy, obejrzyj ten krótki film na YouTube na temat [Przygotowywania nowego dostawcy w Finance and Operations](https://www.youtube.com/watch?v=0KUc3AGaTKk).

## <a name="importing-the-prospective-vendor-registration-request"></a>Importowanie wniosku o rejestrację potencjalnego dostawcy

Wniosek o rejestrację potencjalnego dostawcy to jednostka w rozwiązaniu Supply Chain Management. System można skonfigurować w celu importowania danych za pośrednictwem tej jednostki. 

W poniższej tabeli przedstawiono informacje, który zawiera ta jednostka i które mogą zostać zaimportowane.

| Pole                        | opis |
|------------------------------|-------------|
| Nazwa dostawcy                  | Nazwa dostawcy. |
| Uzasadnienie biznesowe       | Przyczyna lub przyczyny wniosku o nowego dostawcę. |
| Identyfikator organizacji          | Oficjalnie znany numer rejestracyjny. |
| Branża             | Branża, w której prowadzi działalność dostawca. |
| Imię osoby kontaktowej.  | Imię osoby, która zostanie zaproszona do zarejestrowania informacji o dostawcy. |
| Drugie imię osoby kontaktowej | Drugie imię osoby, która zostanie zaproszona do zarejestrowania informacji o dostawcy. |
| Nazwisko osoby kontaktowej   | Nazwisko osoby, która zostanie zaproszona do zarejestrowania informacji o dostawcy. |
| Adres e-mail do osoby kontaktowej       | Adres e-mail, który będzie używany do tworzenia nowego użytkownika w rozwiązaniu Supply Chain Management i zostanie zarejestrowany na koncie Azure Active Directory (Azure AD) dzierżawcy. |
| Data przesłania               | Data utworzenia wniosku w systemie zewnętrznym. |
| Firma                 | Firma, w której dostawca składa wniosek o przyjęcie. Ta wartość musi być kodem firmy, która została zarejestrowana w rozwiązaniu Supply Chain Management. Jeśli w procesie importu nie zostanie odebrana żadna wartość, stosowana jest wartość z parametrów modułu Zaopatrzenie i sourcing. |
| Typ dostawcy                  | Dostawcą może być organizacja lub osoba. Typ dostawcy określa ostateczny sposób jego tworzenia. |

Po zaimportowaniu wniosku o rejestrację potencjalnego dostawcy jest on wyświetlany na stronie listy **Wniosek o rejestrację potencjalnego dostawcy**. Na tej stronie listy specjalista ds. zaopatrzenia może zaprosić użytkownika. Wniosek o przypisanie użytkownika jest wysyłany do przepływu pracy.

## <a name="submitting-a-prospective-vendor-user-request"></a>Przesyłanie wniosku potencjalnego użytkownika-dostawcy

Celem wniosku potencjalnego użytkownika-dostawcy jest określenie osoby, która przesłała początkowy wniosek, aby mogła zalogować się do rozwiązania Supply Chain Management, używając adresu e-mail podanego we wniosku o rejestrację potencjalnego dostawcy.

Wniosek użytkownika potencjalnego użytkownika-dostawcy jest przetwarzany przez przepływ pracy wniosku użytkownika. Ten przepływ pracy komunikuje się za pomocą współpracy B2B usługi Azure AD. Tworzy w rozwiązaniu Supply Chain Management użytkownika, który ma odpowiednie ustawienia zabezpieczeń.

Nowi skonfigurowani użytkownicy mają następujące role zabezpieczeń:

- Zewnętrzny użytkownik systemu
- Potencjalny dostawca (zewnętrzny)

Nowy użytkownik otrzyma wiadomość e-mail wygenerowaną przez przepływ pracy wniosku użytkownika. Ta wiadomość e-mail zawiera zaproszenie użytkownika do zalogowania się do systemu.

Aby uzyskać ogólne informacje o konfiguracji wiadomości e-mail i przepływu pracy, zobacz opis przepływu pracy wniosku użytkownika w temacie [Konfigurowanie i obsługa współpracy z dostawcami](set-up-maintain-vendor-collaboration.md).

## <a name="vendor-registration"></a>Rejestracja dostawcy

Potencjalny użytkownik-dostawca, który zaloguje się w rozwiązaniu Supply Chain Management zobaczy pierwszą stronę Kreatora rejestracji dostawcy, na której może wprowadzić informacje o dostawcy.

Kreator uwzględnia konfigurację wniosku o nowego dostawcę. Kraj lub region, w którym dostawca prowadzi działalność określa, jakie informacje są wymagane w kreatorze i jakie informacje są obowiązkowe.

Aby uzyskać więcej informacji o konfigurowaniu wniosku o nowego dostawcę, zobacz [Konfigurowanie i obsługa współpracy z dostawcami](set-up-maintain-vendor-collaboration.md). W poniższej tabeli przedstawiono przegląd stron w kreatorze oraz celów każdej z nich.

| Strona                       | opis |
|----------------------------|-------------|
| Kraj/region             | Kraj lub region określa konfigurację wniosku o nowego dostawcę, która jest stosowana na pozostałych stronach kreatora. Ponadto określa wartości w wyszukiwaniu wartości **Stan dla podatku**. |
| Postanowienia       | Dostępność tej strony zależy od konfiguracji wniosku o nowego dostawcę. Jeśli jest dostępna, użytkownik musi wyrazić zgodę na warunki i zasady, aby kontynuować. |
| Informacje o dostawcy         | Ta strona zawiera nazwę dostawcy, która jest automatycznie wprowadzana z pierwotnego wniosku o rejestrację potencjalnego dostawcy. Zawiera także numer organizacji, numer telefonu dostawcy, numer faksu i adres e-mail i oraz adresy dostawcy używane do różnych celów. |
| Informacje o osobie kontaktowej | Ta strona zawiera nazwę imię i nazwisko osoby kontaktowej, która jest automatycznie wprowadzana z pierwotnego wniosku o rejestrację potencjalnego dostawcy. Zawiera ona także numer telefonu osoby kontaktowej oraz adres e-mail i adresy używane do różnych celów. |
| Informacje służbowe       | Ta strona zawiera numery identyfikacji podatkowej (różnych krajów lub regionów) i liczbę pracowników. Wskazuje także, czy jest to firma z udziałem mniejszościowym. |
| Kategorie zaopatrzenia     | Ta strona zawiera kategorie zaopatrzenia, dla których dostawca składa wniosek o zatwierdzenie. Użytkownik może wybrać kategorie w hierarchii kategorii zaopatrzenia. W oknie **Parametry modułu Zaopatrzenie i sourcing** &gt; **Portal współpracy z dostawcami** w obszarze **Zaopatrzenie i sourcing** &gt; **Konfiguracja** można skonfigurować liczbę poziomów widocznych w hierarchii. |
| Kwestionariusze             | Kreator może zawierać zestaw kwestionariuszy dla dostawcy. Kwestionariusze widoczne w kreatorze są konfigurowane na wniosek o nowego dostawcę lub według kategorii zaopatrzenia. Jeśli kwestionariuszy są konfigurowane dla kategorii zaopatrzenia, kategorie zaopatrzenia, o których zatwierdzenie wnioskuje dostawca określają kwestionariusze widoczne w kreatorze. Na stronie **Kategoria zaopatrzenia** można dodać kwestionariusz w odpowiedniej kategorii, i ustawić typ działania na **Wdrażanie dostawcy**. |

Po ukończeniu przez potencjalnego użytkownika-dostawcę pracy w kreatorze rejestracji dostawcy tworzony jest wniosek o nowego dostawcę.

## <a name="manually-or-automatically-submit-a-vendor-request"></a>Ręczne lub automatyczne przesyłanie wniosku o nowego dostawcę

Wniosek o nowego dostawcę można utworzyć jako wersję roboczą i ręcznie przesłać do przepływu pracy. Wniosek o nowego dostawcę można także automatycznie przesłać do przepływu pracy po zakończeniu działania kreatora rejestracji dostawcy. Wniosek można przesłać ręcznie, jeżeli na przykład specjalista ds. zaopatrzenia chce ocenić, czy wniosek ma zostać skierowany do procesu zatwierdzenia przed przesłaniem do przepływu pracy.

- Wybierz opcję **Parametry modułu Zaopatrzenie i sourcing** &gt; **Portal współpracy z dostawcami** , a następnie **Automatyczne przesyłanie rejestracji potencjalnego dostawcy do przepływu pracy** , aby skonfigurować wniosek o nowego dostawcę w celu automatycznego przesyłania do przepływu pracy po ukończeniu pracy kreatora rejestracji dostawcy.

## <a name="vendor-requests"></a>Zgłoszenia dostawcy

Wnioski o nowego dostawcę są dostępne na stronie na stronie **Żądania użytkowników portalu współpracy z dostawcami**.

Wniosek o nowego dostawcę zawiera informacje wprowadzone przez potencjalnego użytkownika-dostawcę w kreatorze rejestracji dostawcy.

Wniosek umożliwia sprawdzenie informacji o dostawcy i określenie czy dostawca ma zostać zarejestrowany.

Wniosek o nowego dostawcę należy przesłać do przepływu pracy, a następnie rozesłać do odpowiednich osób sprawdzających i zatwierdzających. Aby uzyskać podstawowe informacje o konfigurowania przepływu pracy zobacz [Przepływy pracy dla zaopatrzenia i sourcingu](procurement-sourcing-workflows.md).

W poniższej tabeli przedstawiono stany, jakie mogą mieć wnioski o nowego dostawcę.

| Stan                     | opis |
|----------------------------|-------------|
| Robocza                      | Wniosek o nowego dostawcę jeszcze nie został przesłany. |
| Wniosek przesłany          | Wniosek o nowego dostawcę został przesłany, a pierwszy krok w przepływie pracy jest przetwarzany. |
| Oczekuje na przegląd             | Jeżeli w zadaniu przepływu pracy jest wiele osób sprawdzających, osoba sprawdzająca może zaakceptować zadanie sprawdzania wniosku o nowego dostawce, a następnie ukończyć sprawdzanie. Jeśli jest tylko jedna osoba sprawdzająca, taki uczestnik może ukończyć sprawdzanie, wybierając opcję **Ukończone** w akcji przepływu pracy. Nie musi najpierw akceptować elementu pracy. |
| Wniosek oczekuje na zatwierdzenie   | Wniosek o nowego dostawcę został rozesłany do uczestników w celu zatwierdzenia i dostępna jest opcja wnioskowania o dodatkowe informacje. Wniosek o dodatkowe informacje powoduje przesłanie elementu pracy z powrotem do osoby przesyłającej. W tym stanie wniosek o nowego dostawcę może również zostać zatwierdzony lub odrzucony. |
| Podanie o zmianę we wniosku | Osoba zatwierdzająca poprosiła o dodatkowe informacje, a wniosek o nowego dostawcę został przesłany do osoby, która wysłała wniosek o nowego dostawcę. Osoba wysyłająca może dodać wymagane informacje, a następnie ponownie wysłać wniosek o nowego dostawcę. Jeżeli wniosek o nowego dostawce zostanie wysłany ponownie, jego stan zmienia się z powrotem na **Wniosek oczekuje na zatwierdzenie**. |
| Wniosek zatwierdzony           | Ten stan jest stanem końcowym. |
| Wniosek odrzucony           | Ten stan jest stanem końcowym. |

## <a name="approving-a-vendor-request"></a>Zatwierdzanie wniosku o nowego dostawcę

Po zatwierdzeniu wniosku o nowego dostawcę następuje utworzenie konta dostawcy, a stan **Zatwierdzone** pojawia się w początkowym wniosku o rejestrację potencjalnego dostawcy i wniosku o nowego dostawcę.

Przed zatwierdzeniem wniosku o nowego dostawcę na stronie **Nowy dostawca** na skróconej karcie **Ogólne** wybierz opcję **Grupa dostawców** , aby wybrać grupę dostawców.

Jeżeli potencjalny użytkownik-dostawca ma mieć dostęp do rozwiązania Supply Chain Management jako użytkownik współpracujący z dostawcą, który go reprezentuje, ustaw uprawnienie dostępu współpracy z dostawcą na **Tak**. Aby dezaktywować konto użytkownika, które potencjalnego dostawca użył do rejestrowania, ustaw uprawnienie na **Nie**.

Jeżeli uprawnienie dostępu współpracy z dostawcą jest ustawione na **Tak** , po zatwierdzeniu wniosku o nowego dostawcę przesyłany jest wniosek o modyfikację ról użytkownika tak, aby miał on role zdefiniowane dla typu **Dostawca** w obszarze **Role zewnętrzne**. Jeśli to uprawnienie jest ustawione na **Nie** , po zatwierdzeniu wniosku o nowego dostawcę wysyłany jest wniosek o dezaktywację użytkownika. W takim przypadku należy skonfigurować przepływ pracy dezaktywowania wniosku użytkownika.

Aby utworzyć konto dostawcy po zatwierdzeniu wniosku o nowego dostawcę należy ustawić sekwencję numerów tworzenia dostawców na podstawie wniosków o nowego dostawcę na **Auto**.

Przegląd uprawnień dostępu użytkownika współpracy z dostawcą zawiera temat [Konfigurowanie i obsługa współpracy z dostawcami](set-up-maintain-vendor-collaboration.md).

## <a name="rejecting-a-vendor-request"></a>Odrzucanie wniosku o nowego dostawcę

W przypadku odrzucenia wniosku o nowego dostawcę należy wybrać przyczynę odrzucenia w wniosku o nowego dostawcę.

Po odrzuceniu wniosku o nowego dostawcę wysyłany jest wniosek o dezaktywację użytkownika. W takim przypadku należy skonfigurować przepływ pracy dezaktywowania wniosku użytkownika. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie i obsługa współpracy z dostawcami](set-up-maintain-vendor-collaboration.md).

Po odrzuceniu wniosku o nowego dostawcę stan **Odrzucone** pojawia się w początkowym wniosku o rejestrację potencjalnego dostawcy i wniosku o nowego dostawcę.

## <a name="deleting-a-prospective-vendor-registration-request-in-various-statuses"></a>Usuwanie wniosku o rejestrację potencjalnego dostawcy w różnych stanach

Różne stany wniosku o rejestrację potencjalnego dostawcy określają stan postępu realizacji wniosku.

Wybierając akcję **Usuń** we wniosku o rejestrację potencjalnego dostawcy można wyczyścić i usunąć łańcuch utworzonych rekordów i dezaktywować konto użytkownika. Wynik wykonania akcji **Usuń** zależy od stanu wniosku o rejestrację potencjalnego dostawcy, jak pokazano w poniższej tabeli.


|          Stan          |                                                                                     Opis stanu                                                                                      |                                                                                                                                                            Wynik akcji Usuń                                                                                                                                                             |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           Nowy            |                                                                         Nie wykonano żadnych akcji dotyczących wniosku.                                                                          |                                                                                                                                              Wniosek o rejestrację potencjalnego dostawcy jest usuwany.                                                                                                                                               |
|      Wnioskowane przez użytkownika      | Po wybraniu opcji <strong>Zaproś użytkownika</strong> stan jest zmieniany na <strong>Wnioskowane przez użytkownika</strong> i następuje utworzenie oraz przesłanie wniosku o potencjalnego użytkownika do przepływu pracy wniosku o nowego użytkownika. |                                                                                                          Wniosku o rejestrację potencjalnego dostawcy w tym stanie nie można usunąć, ponieważ przepływ pracy wniosku użytkownika nie zakończył się.                                                                                                          |
|       Zaproszony użytkownik       |                                                               Przepływ pracy wniosku o nowego użytkownika został zatwierdzony, a użytkownik został utworzony.                                                               |                                                                                                                      Został utworzony wniosek o dezaktywowanie użytkownika i wniosek o rejestrację potencjalnego dostawcy został usunięty.                                                                                                                      |
| Rejestracja w toku |                                                         Nowy użytkownik zalogował się i uruchomił kreatora rejestracji dostawcy.                                                          |                                                                                     Wniosek o dezaktywację użytkownika został utworzony, a wniosek o rejestracje potencjalnego dostawcy i dane wprowadzone w kreatorze rejestracji dostawcy zostały usunięte.                                                                                      |
|  Utworzono wniosek o nowego dostawcę  |                                                                     Praca kreatora rejestracji dostawcy została ukończona.                                                                      | Wniosek o dezaktywację użytkownika został utworzony, a wniosek o rejestracje potencjalnego dostawcy, dane wprowadzone w kreatorze rejestracji dostawcy i wniosek o nowego dostawcę zostały usunięte.<blockquote>[!NOTE]<br>Akcji <strong>Usuń</strong> nie można użyć, gdy wniosek o nowego dostawce jest w trakcie procesu przeglądu w przepływie pracy.</blockquote> |
|         Zatwierdzona         |                                                                               Wniosek o nowego dostawcę został zatwierdzony.                                                                               |                                                                                                   Wniosek o rejestracje potencjalnego dostawcy, dane wprowadzone w kreatorze rejestracji dostawcy i wniosek o nowego dostawcę zostały usunięte.                                                                                                    |
|         Odrzucona         |                                                                               Wniosek o nowego dostawcę został odrzucony.                                                                               |                                                                                                   Wniosek o rejestracje potencjalnego dostawcy, dane wprowadzone w kreatorze rejestracji dostawcy i wniosek o nowego dostawcę zostały usunięte.                                                                                                    |

