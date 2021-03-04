---
title: Ustawienie uprawnień użytkowników w aplikacji Attract
description: Ten temat zawiera informacje na temat zabezpieczeń na podstawie ról w aplikacji Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: efac512cfa07bb2183f06b8be45f74bef9af0767
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462221"
---
# <a name="set-user-permissions-in-attract"></a>Ustawienie uprawnień użytkowników w aplikacji Attract

[!include [banner](includes/banner.md)]

Aplikacja Microsoft Dynamics 365 Talent: Attract używa zabezpieczeń opartych na rolach. Innymi słowy dostęp nie jest przyznawany poszczególnym użytkownikom, ale rolom zabezpieczeń, do których są przypisywani użytkowników. Użytkownik, którego przypisano do roli zabezpieczeń, ma dostęp do zbioru uprawnień skojarzonego z tą rolą.

Aplikacja Attract oferuje pięć podstawowych ról użytkownika:

- Administrator
- Menedżer zatrudniający
- Osoba rekrutująca
- Osoba przeprowadzająca rozmowę kwalifikacyjną
- Tylko do odczytu

Rola Administrator jest jedyną rolą, która ma uprawnienia do dodawania innych użytkowników i zmieniania ich uprawnień.

- **Dodawanie** — W Centrum administracyjnym na karcie **Uprawnienia użytkownika** wybierz opcję **Przypisz role**, poszukaj użytkownika, którego chcesz dodać, a następnie przypisz uprawnienia temu użytkownikowi.
- **Edytowanie** — Wyszukaj użytkownika lub znajdź go na liście, a następnie wybierz opcję **Edytuj**, aby zmienić jego uprawnienia.
- **Usuwanie** — Usunięcie uprawnień użytkownika nie powoduje usunięcia użytkownika z systemu. Ograniczysz jednak użytkownikowi dostęp i uprawnienia w aplikacji Attract. Na przykład Helenę przypisano do roli Menedżer zatrudniający oraz dodano do funkcji jako menedżera zatrudniającego. Jeśli Helena później zostanie usunięta z roli Menedżer zatrudniający, pozostanie menedżerem zatrudniającym w funkcji i nadal będzie mieć dostęp do tej funkcji. Nie może jednak tworzyć innych funkcji.

Poniższe sekcje zawierają ogólne opisy poszczególnych ról. Tabele w dalszej części tematu zawierają bardziej szczegółowe informacje.

> [!NOTE]
> Niektóre opcje są dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji dla aplikacji Attract.

## <a name="administrator"></a>Administrator

Użytkownicy przypisani do roli Administrator mogą uzyskiwać dostęp do wszystkich danych w aplikacji Attract oraz je zmieniać. Administratorzy mogą tworzyć, czytać, aktualizować i usuwać dane. Mają również dostęp do Centrum administracyjnego, gdzie mogą konfigurować Attract i wprowadzać dane użytkowników. Zalecamy, aby co najmniej jedną osobę przypisać do roli Administrator. Domyślnie administrator środowiska w usłudze Microsoft Power Apps jest ustawiony jako administrator w aplikacji Attract. Jeśli zasubkrybujesz wersję próbną aplikacji Attract, rola Administrator jest Ci przypisywana automatycznie. Obecnie w celu tworzenia zadań użytkownicy, którzy mają rolę Administrator, muszą mieć dodatkowo rolę Osoba rekrutująca lub Menedżer zatrudniający.

## <a name="hiring-manager"></a>Menedżer zatrudniający

Użytkownicy przypisani do roli Menedżer zatrudniający mogą tworzyć funkcje oraz aktualizować funkcje, które wcześniej sami utworzyli. Menedżerowie zatrudniający mogą wykonywać tylko ograniczony zbiór czynności na funkcji oraz na zgłoszeniach skojarzonych z tą funkcją. Tylko użytkownicy przypisani do roli Menedżer zatrudniający mogą być dodawani do zespołu rekrutacyjnego jako menedżerowie zatrudniający.

## <a name="recruiter-role"></a>Osoba rekrutująca

Użytkownicy przypisani do roli Osoba rekrutująca mają pełne uprawnienia odczytu, tworzenie, aktualizowania i usuwania uprawnień wobec funkcji, które utworzyli. Mają również pełne uprawnienia tworzenia, odczytu, aktualizowania i usuwania wobec zgłoszeń skojarzonych z funkcjami, których są właścicielami. Tylko użytkownicy przypisani do roli Osoba rekrutująca mogą być dodawani do zespołu rekrutacyjnego jako osoby rekrutujące.

## <a name="interviewer"></a>Osoby przeprowadzającej rozmowę kwalifikacyjną

Każdy użytkownik, który ma konto w usłudze Microsoft Azure Active Directory (Azure AD) w organizacji, może zostać dodany do zespołu rekrutacyjnego jako osoba przeprowadzającą rozmowę kwalifikacyjną. Użytkownicy przypisani do roli Osoba przeprowadzająca rozmowę kwalifikacyjną mogą wyświetlać szczegóły funkcji i dane kandydatów dla funkcji, z powodu których znaleźli się w zespole rekrutacyjnym. Dla tych funkcji osoby przeprowadzające rozmowy kwalifikacyjne mogą również formułować rekomendacje zatrudnienia i wystawiać opinie o kandydatach. Nie mogą jednak aktualizować szczegółów funkcji ani danych kandydatów.

## <a name="read-only"></a>Tylko do odczytu

Użytkownicy przypisani do roli Tylko do odczytu mają dostęp tylko do odczytu do wszystkich danych w środowisku Attract. Nie mogą jednak tworzyć ani edytować żadnych danych.

## <a name="find-out-which-roles-you-have"></a>Dowiedz się, które role masz

1.  W Attract kliknij znak zapytania (**?**) w prawym górnym rogu strony.

2.  Kliknij przycisk **Informacje**.

    W wyświetlonym oknie zobaczysz wszystkie role, jakie masz w Attract:

    ![Wyświetl typ licencji użytkownika Attract](media/attract-license-types.png)
    
## <a name="delegated-roles"></a>Role delegowane

Dla każdego stanowiska, z którego powodu znajdują się w zespole rekrutacyjnym, osoby rekrutujące i menedżerowie zatrudniający mogą wyznaczyć jednego lub kilku swoich delegatów (pełnomocników, użytkowników delegowanych). Nie mogą jednak wyznaczać pełnomocników innych osób w zespole rekrutacyjnym.

Pełnomocnicy mają takie same uprawnienia, jak osoba, która ich wyznaczyła. Na przykład jeśli menedżer zatrudniający wyznaczy swojego pełnomocnictwa dla funkcji, pełnomocnik będzie miał takie same uprawnienia, jak menedżer zatrudniający dla tej funkcji. Użytkownicy delegowani nie mogą usuwać innych użytkowników delegowanych z zespołu rekrutacyjnego. Nie mogą również usuwać osób, które wyznaczyły ich na pełnomocników.

## <a name="job-details-and-actions"></a>Szczegóły funkcji i dostępne czynności

Użytkownicy, którzy mają rolę Osoba rekrutująca lub Menedżer zatrudniający, mogą tworzyć funkcje. Następujące uprawnienia dotyczą szczegółów funkcji oraz czynności, jakie można wykonywać na funkcjach.

| Dane lub czynność    | Osoba rekrutująca | Menedżer zatrudniający | Osoba przeprowadzająca rozmowę kwalifikacyjną |
|-------------------|-----------|----------------|-------------|
| Szczegóły funkcji       | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tylko do odczytu |
| Zespół rekrutacyjny       | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tylko do odczytu |
| Oferta pracy       | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tylko do odczytu | Tylko do odczytu |
| Przetwarzaj           | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tylko do odczytu |
| Dodawanie kandydatów    | Dodawanie kandydatów do funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Dodawanie kandydatów do funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Niedozwolone |
| Dodawanie prospektów     | Dodawanie prospektów do funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | W [konfiguracji działań prospektów](./activities-attract.md#prospect-activity) znajduje się opcja określająca, czy osoby przeprowadzające rozmowy kwalifikacyjne mogą dodawać i wyświetlać prospektów. | Niedozwolone |
| Aktywacja funkcji      | Aktywowanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Aktywowanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Niedozwolone |
| Zamknij funkcję         | Zamykanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Niedozwolone | Niedozwolone |
| Usuwanie zadania        | Usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tylko wtedy, gdy do funkcji nie dodano żadnych kandydatów | Niedozwolone |
| Usuwanie kandydatów | Usuwanie kandydatów, jeśli użytkownik znajduje się w zespole rekrutacyjnym | Niedozwolone | Niedozwolone |

## <a name="application-details-and-actions"></a>Szczegóły zgłoszeń i dostępne czynności

Następujące uprawnienia dotyczą danych specyficznych dla funkcji mających zastosowanie do kandydatów oraz czynności, jakie można wykonywać na zgłoszeniach.

| Dane lub czynność          | Osoba rekrutująca | Menedżer zatrudniający | Osoba przeprowadzająca rozmowę kwalifikacyjną |
|-------------------------|-----------|----------------|-------------|
| Dokumenty zgłoszeń   | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tylko do odczytu |
| Uwagi do zgłoszeń       | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tworzenie, odczyt, aktualizowanie i usuwanie funkcji, z powodu których użytkownik znalazł się w zespole rekrutacyjnym | Tylko do odczytu|
| Działania na zgłoszeniach    | Wyświetlanie, jeśli użytkownik znajduje się w zespole rekrutacyjnym | Wyświetlanie, jeśli użytkownik znajduje się w zespole rekrutacyjnym | Tylko do odczytu |
| Opinie o zgłoszeniach    | Dodawanie i wyświetlanie wszystkich opinii, jeśli użytkownik należy do zespołu rekrutacyjnego | Dodawanie i wyświetlanie wszystkich opinii, jeśli użytkownik należy do zespołu rekrutacyjnego | Może dodawać opinie\*\* |
| Odrzucanie zgłoszeń      | Może odrzucać, jeśli znajduje się w zespole rekrutacyjnym | Niedozwolone | Niedozwolone |
| Przenieś na kolejny etap           | Może odrzucać, jeśli znajduje się w zespole rekrutacyjnym | Może przekazywać do kolejnego etapu, jeśli znajduje się w zespole rekrutacyjnym | Niedozwolone |
| Uruchamianie aplikacji zarządzania ofertami | Może uruchamiać aplikację zarządzania ofertami | Istnieje opcja konfiguracji w działaniu Oferta. | Niedozwolone |


\*\* Opcja konfiguracji w [ustawieniach działań na opiniach](./activities-attract.md) decyduje, czy osoby przeprowadzające rozmowy kwalifikacyjne widzą nawzajem swoje opinie.


## <a name="process-templates"></a>Szablony procesów

Następujące uprawnienia mają zastosowanie do szablonów procesu rektutacji. Zdolność członków zespołu do tworzenia i edytowania szablonów jest konfigurowana w sekcji **Zarządzanie szablonami** w Centrum administracyjnym. Jeśli funkcja zarządzania szablonami jest włączona, osoby rekrutujące i menedżerowie zatrudniający mogą tworzyć i edytować własne szablony procesów. Jeśli funkcja zarządzania szablonami jest wyłączona, tylko administratorzy mogą tworzyć i edytować szablony procesów. W poniższej tabeli założono, że funkcja zarządzania szablonami jest włączona.

| Dane              | Osoba rekrutująca                                           | Menedżer zatrudniający                                      | Osoba przeprowadzająca rozmowę kwalifikacyjną |
|-------------------|-----------------------------------------------------|-----------------------------------------------------|-------------|
| Szablony procesów | Pełne uprawnienia wobec szablonów utworzonych przez użytkownika | Pełne uprawnienia wobec szablonów utworzonych przez użytkownika | Brak dostępu   |

## <a name="email-and-email-templates"></a>Wiadomości e-mail i szablony wiadomości e-mail

Następujące uprawnienia dotyczą szablonów wiadomości e-mail oraz czynności, jakie można wykonywać na wiadomościach e-mail. Tylko administratorzy mogą tworzyć i edytować szablony wiadomości e-mail.

| Dane lub czynność     | Osoba rekrutująca          | Menedżer zatrudniający     | Osoba przeprowadzająca rozmowę kwalifikacyjną |
|--------------------|--------------------|--------------------|-------------|
| Szablony wiadomości e-mail    | Dostęp tylko do odczytu   | Dostęp tylko do odczytu   | Brak dostępu   |
| Wyślij wiadomość e-mail         | Wysyłanie dla poszczególnych działań  | Wysyłanie dla poszczególnych działań  | Brak dostępu   |
| Edytowanie treść wiadomości e-mail | Edytowanie treść wiadomości e-mail | Edytowanie treść wiadomości e-mail | Brak dostępu   |

## <a name="talent-pools"></a>Pule umiejętności

Następujące uprawnienia mają zastosowanie do pul umiejętności. Pule umiejętności są widoczne tylko dla osób, które je utworzyły, chyba że dana osoba postanowi je udostępnić. Funkcja wyszukiwania kandydatów może służyć do znajdowania kandydatów, których jeszcze nie dodano do nazwanej puli.

| Dane lub czynność   | Osoba rekrutująca                                       | Menedżer zatrudniający                                  | Osoba przeprowadzająca rozmowę kwalifikacyjną |
|------------------|-------------------------------------------------|-------------------------------------------------|-------------|
| Nazwana pula       | Pełne uprawnienia wobec pul utworzonych przez użytkownika | Pełne uprawnienia wobec pul utworzonych przez użytkownika | Brak dostępu   |
| Udostępnianie puli       | Tylko pule utworzone przez użytkownika                | Tylko pule utworzone przez użytkownika                | Brak dostępu   |
| Wyszukiwanie kandydatów | Pełne funkcje wyszukiwania                        | Pełne funkcje wyszukiwania                        | Brak dostępu   |

## <a name="candidates"></a>Kandydaci

Kandydaci to osoby, które zostały dodane do puli umiejętności, ale nie są skojarzone z funkcją.

| Dane                        | Osoba rekrutująca                        | Menedżer zatrudniający                   | Osoba przeprowadzająca rozmowę kwalifikacyjną |
|-----------------------------|----------------------------------|----------------------------------|-------------|
| Profil — szczegóły kandydata | Tworzenie, odczyt, aktualizowanie i usuwanie | Tworzenie, odczyt, aktualizowanie i usuwanie | Brak dostępu   |
| Dokumenty                   | Tworzenie, odczyt, aktualizowanie i usuwanie | Tworzenie, odczyt, aktualizowanie i usuwanie | Brak dostępu   |


[!INCLUDE[footer-include](../includes/footer-banner.md)]