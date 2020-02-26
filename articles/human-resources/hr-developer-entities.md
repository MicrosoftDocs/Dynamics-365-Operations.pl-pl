---
title: Jednostki usługi Common Data Service
description: Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Common Data Service do obsługi scenariuszy rozszerzalności i integracji.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85dd95e8209fff28f214986f7960372db200351b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010251"
---
# <a name="common-data-service-entities"></a>Jednostki usługi Common Data Service

Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Common Data Service do obsługi scenariuszy rozszerzalności i integracji.

Aby uzyskać więcej informacji dotyczących usługi Common Data Service, zobacz temat [Co to jest usługa Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

W usłudze Common Data Service są dostępne są następujące jednostki aplikacji Human Resources.

## <a name="benefit-entities"></a>Jednostki dotyczące świadczeń

**Częstotliwość obliczania świadczeń**

| **Pola**        | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------------|---------------|--------------|----------------|
| Opis       | Tekst          |              | X              |
| Kontrola częstotliwości | Zestaw opcji    | X            | X              |
| Niezmienne      | Dwie opcje   |              | X              |
| Nazwisko              | Tekst          | X            | X              |


**Stawka obliczania świadczenia**

| **Pola**  | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------|---------------|--------------|----------------|
| Opis | Tekst          |              | X              |
| Nazwisko        | Tekst          | X            | X              |
| Typ warstwy    | Zestaw opcji    | X            | X              |


**Szczegół stawki obliczania świadczenia**

| **Pola**                             | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|----------------------------------------|----------------|--------------|----------------|
| Numer pozycji stawki obliczania świadczenia | Tekst           | X            | X              |
| Identyfikator stawki obliczania                    | Wyszukiwanie         | X            | X              |
| Metoda udziału                    | Zestaw opcji     | X            | X              |
| Weszła w życie                              | Tylko data      | X            | X              |
| Udział pracodawcy                  | Liczba dziesiętna |              | X              |
| Data ważności                             | Tylko data      | X            | X              |
| Potrącenie pracownika                        | Liczba dziesiętna |              | X              |


**Typ świadczenia**

| **Pola**           | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|----------------------|---------------|--------------|----------------|
| Rejestrowanie współbieżne | Zestaw opcji    |              | X              |
| Opis          | Tekst          |              | X              |
| Nazwisko                 | Tekst          | X            | X              |
| Kategoria listy płac      | Zestaw opcji    |              | X              |


**Plan świadczeń**

| **Pola**                               | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|------------------------------------------|----------------|--------------|----------------|
| Metoda limitu zaległości                      | Zestaw opcji     |              | X              |
| Typ świadczenia                             | Wyszukiwanie         | X            | X              |
| Metoda limitu udziału                | Zestaw opcji     |              | X              |
| Metoda udziału                      | Zestaw opcji     |              | X              |
| Waluta                                 | Wyszukiwanie         |              | X              |
| Priorytet potrącenia                       | Liczba całkowita   |              | X              |
| Domyślna kwota limitu udziału        | Waluta       |              | X              |
| Domyślna kwota limitu udziału (podstawa) | Waluta       |              | X              |
| Domyślny okres limitu udziału        | Zestaw opcji     |              | X              |
| Domyślna kwota limitu potrącenia           | Waluta       |              | X              |
| Domyślna kwota limitu potrącenia (podstawa)    | Waluta       |              | X              |
| Domyślny okres limitu potrącenia           | Zestaw opcji     |              | X              |
| Opis                              | Tekst           |              | X              |
| Kurs wymiany                            | Liczba dziesiętna |              | X              |
| Dodatkowa sesja kalkulacji płac                | Dwie opcje    |              | X              |
| Do zgłoszenia według ACA        | Dwie opcje    |              | X              |
| Wygenerowano zaległości                      | Dwie opcje    |              | X              |
| Zwiększenie wartości brutto                              | Dwie opcje    |              | X              |
| Główne                               | Dwie opcje    |              | X              |
| Nazwisko                                     | Tekst           | X            | X              |
| Wpływ na listę płac                           | Zestaw opcji     |              | X              |
| Typ emerytury                          | Zestaw opcji     |              | X              |


**Jednostka Zatrudnienie**

| **Pola**                     | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|--------------------------------|----------------|--------------|----------------|
| Skorygowana data rozpoczęcia pracownika     | Data i godzina  |              | X              |
| Firma                        | Wyszukiwanie         | X            | X              |
| Kwota jednostki wypowiedzenia pracodawcy | Liczba dziesiętna |              | X              |
| Jednostka wypowiedzenia pracodawcy        | Zestaw opcji     |              | X              |
| Data zakończenia zatrudnienia            | Data i godzina  |              | X              |
| Numer etatu              | Tekst           | X            | X              |
| Data rozpoczęcia zatrudnienia          | Data i godzina  |              | X              |
| Data ostatniego dnia pracy              | Data i godzina  |              | X              |
| Data przejścia                | Data i godzina  |              | X              |
| Początek ważności                     | Data i godzina  | X            | X              |
| Koniec ważności                       | Data i godzina  |              | X              |
| Pracownik                         | Wyszukiwanie         | X            | X              |
| Kwota wypowiedzenia pracownika           | Liczba dziesiętna |              | X              |
| Data rozpoczęcia pracownika             | Data i godzina  |              | X              |
| Typ pracownika                    | Zestaw opcji     | X            | X              |
| Jednostka wypowiedzenia pracownika          | Zestaw opcji     |              | X              |

## <a name="worker-entities"></a>Jednostki dotyczące pracownika

**Pochodzenie etniczne**

| **Pola**         | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|--------------------|---------------|--------------|----------------|
| Opis        | Tekst          |              | X              |
| Nazwa pochodzenia etnicznego | Tekst          | X            | X              |


**Język**

| **Pola**    | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|---------------|---------------|--------------|----------------|
| Opis   | Tekst          |              | X              |
| Nazwa języka | Tekst          | X            | X              |


**Status kombatanta**

| **Pola**           | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|----------------------|---------------|--------------|----------------|
| Opis          | Tekst          |              | X              |
| Chroniony kombatant | Dwie opcje    |              | X              |
| Nazwa języka        | Tekst          | X            | X              |


**Pracownik**

| **Pola**                | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|---------------------------|---------------|--------------|----------------|
| Data urodzenia                 | Tylko data     |              | X              |
| Opis               | Tekst          |              | X              |
| Adres e-mail 1           | E-mail         |              | X              |
| Adres e-mail 2           | E-mail         |              | X              |
| Tożsamość w serwisie Facebook         | Tekst          |              | X              |
| Imię                | Tekst          |              | X              |
| Imię i nazwisko                 | Tekst          |              | X              |
| Rodzaj                    | Zestaw opcji    |              | X              |
| Pokolenie                | Tekst          |              | X              |
| Dozwolony kontakt przez e-mail  | Dwie opcje   |              | X              |
| Dozwolony kontakt telefoniczny  | Dwie opcje   |              | X              |
| Nazwisko                 | Tekst          |              | X              |
| Tożsamość na LinkedIn         | Tekst          |              | X              |
| Menedżer                   | Wyszukiwanie        |              | X              |
| Drugie imię               | Tekst          |              | X              |
| Telefon komórkowy              | Telefon         |              | X              |
| Identyfikator usługi Office Graph   | Tekst          |              | X              |
| Podstawowy adres e-mail     | E-mail         |              | X              |
| Podstawowy numer telefonu         | Telefon         |              | X              |
| Zawód                | Tekst          |              | X              |
| Sieć społecznościowa 1          | Zestaw opcji    |              | X              |
| Sieć społecznościowa 2          | Zestaw opcji    |              | X              |
| Tożsamość w sieci społecznościowej 1 | Tekst          |              | X              |
| Tożsamość w sieci społecznościowej 2 | Tekst          |              | X              |
| Źródło                    | Zestaw opcji    | X            | X              |
| Stan                    | Zestaw opcji    | X            | X              |
| Telefon 1               | Telefon         |              | X              |
| Telefon 2               | Telefon         |              | X              |
| Telefon 3               | Telefon         |              | X              |
| Tożsamość na Twitterze          | Tekst          |              | X              |
| Użytkownik                      | Wyszukiwanie        |              | X              |
| Adres URL witryny sieci Web               | Adres URL           |              | X              |
| Numer pracownika             | Tekst          | X            | X              |
| Typ pracownika               | Zestaw opcji    | X            | X              |
| Imię na Yomi           | Tekst          |              | X              |
| Imię i nazwisko na Yomi            | Tekst          |              | X              |
| Nazwisko na Yomi            | Tekst          |              | X              |
| Drugie imię na Yomi          | Tekst          |              | X              |


**Adres pracownika**

| **Pola**           | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|----------------------|----------------|--------------|----------------|
| Numer domu       | Tekst           | X            | X              |
| Typ adresu         | Zestaw opcji     | X            | X              |
| Miejscowość                 | Tekst           |              | X              |
| Kraj lub region    | Tekst           |              | X              |
| Powiat               | Tekst           |              | X              |
| Faks                  | Telefon          |              | X              |
| Preferowane         | Dwie opcje    |              | X              |
| Szerokość geograficzna             | Liczba dziesiętna |              | X              |
| Wiersz 1               | Tekst           |              | X              |
| Wiersz 2               | Tekst           |              | X              |
| Wiersz 3               | Tekst           |              | X              |
| Długość geograficzna            | Liczba dziesiętna |              | X              |
| Kod pocztowy          | Tekst           |              | X              |
| Skrzynka pocztowa      | Tekst           |              | X              |
| Kod metody wysyłki | Liczba całkowita   |              | X              |
| Województwo    | Tekst           |              | X              |
| Telefon 1          | Telefon          |              | X              |
| Telefon 2          | Telefon          |              | X              |
| Telefon 3          | Telefon          |              | X              |
| Strefa UPS             | Tekst           |              | X              |
| Przesunięcie względem czasu UTC           | Liczba całkowita   |              | X              |
| Pracownik               | Wyszukiwanie         | X            | X              |


**Dane osobowe pracownika**

| Pola                             | Typ danych    | Potrzebne | Z możliwością wyszukiwania |
|------------------------------------|--------------|----------|------------|
| Miejscowość urodzenia                         | Tekst         |          | X          |
| Kraj lub region urodzenia            | Zestaw opcji   |          | X          |
| Data urodzenia                          | Tylko data    |          | X          |
| Kraj lub region obywatelstwa      | Zestaw opcji   |          | X          |
| Data zgonu                      | Tylko data    |          | X          |
| Data weryfikacji niepełnosprawności kombatanta | Tylko data    |          | X          |
| Oświata                          | Tekst         |          | X          |
| Pochodzenie etniczne                     | Wyszukiwanie       |          | X          |
| Data zakończenia ekspatriacji                  | Tylko data    |          | X          |
| Data rozpoczęcia ekspatriacji                | Tylko data    |          | X          |
| Kraj lub region urodzenia ojca     | Zestaw opcji   |          | X          |
| Rodzaj                             | Zestaw opcji   |          | X          |
| Niepełnosprawny                        | Dwie opcje  |          | X          |
| Kombatant niepełnosprawny                | Dwie opcje  |          | X          |
| Ma zastosowanie orzeczenie o ekspatriacji    | Dwie opcje  |          | X          |
| Student w pełnym wymiarze               | Dwie opcje  |          | X          |
| Stan cywilny                     | Zestaw opcji   |          | X          |
| Data zakończenia służby wojskowej          | Tylko data    |          | X          |
| Data rozpoczęcia służby wojskowej        | Tylko data    |          | X          |
| Kraj lub region urodzenia matki     | Zestaw opcji   |          | X          |
| Kraj lub region narodowości      | Zestaw opcji   |          | X          |
| Język ojczysty                    | Wyszukiwanie       |          | X          |
| Liczba osób na utrzymaniu               | Liczba całkowita |          |            |
| Status kombatanta                     | Wyszukiwanie       |          | X          |
| Pracownik                             | Wyszukiwanie       | X        | X          |
| Numer pozycji danych osobowych pracownika      | Tekst         | X        | X          |


**Konto bankowe pracownika**

| **Pola**                 | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|----------------------------|---------------|--------------|----------------|
| Posiadacz konta             | Tekst          |              | X              |
| Identyfikacja konta     | Tekst          |              | X              |
| Opis adresu        | Tekst          |              | X              |
| Typ konta bankowego          | Zestaw opcji    |              | X              |
| Kod lokalizacji banku         | Tekst          |              | X              |
| Nazwa oddziału                | Tekst          |              | X              |
| Numer oddziału              | Tekst          |              | X              |
| Miejscowość                       | Tekst          |              | X              |
| Kraj lub region          | Tekst          |              | X              |
| Powiat                     | Tekst          |              | X              |
| Opis                | Tekst          |              | X              |
| Nazwa okręgu              | Tekst          |              | X              |
| E-mail                      | Tekst          |              | X              |
| Wewnętrzny                  | Tekst          |              | X              |
| Faks                        | Tekst          |              | X              |
| Numer IBAN                       | Tekst          |              | X              |
| Wiersz 1                     | Tekst          |              | X              |
| Wiersz 2                     | Tekst          |              | X              |
| Wiersz 3                     | Tekst          |              | X              |
| Telefon komórkowy               | Tekst          |              | X              |
| Nazwisko pracownika             | Tekst          |              | X              |
| Kod pocztowy                | Tekst          |              | X              |
| Skrzynka pocztowa            | Tekst          |              |                |
| Kod banku             | Tekst          |              | X              |
| Typ kodu banku        | Zestaw opcji    |              | X              |
| Województwo          | Tekst          |              | X              |
| Kod SWIFT                 | Tekst          |              | X              |
| Telefon                  | Tekst          |              | X              |
| Numer teleksu               | Tekst          |              | X              |
| Adres URL witryny sieci Web                | Tekst          |              | X              |
| Pracownik                     | Wyszukiwanie        | X            | X              |
| Numer konta bankowego pracownika | Tekst          |              | X              |
| Numer konta bankowego pracownika | Tekst          | X            | X              |

**Stałe wynagrodzenie pracownika**

| Pola                                | Typ danych      | Potrzebne | Z możliwością wyszukiwania |
|---------------------------------------|----------------|----------|------------|
| Firma                               | Wyszukiwanie         | X        | X          |
| Typ wynagrodzenia                     | Zestaw opcji     |          | X          |
| Waluta                              | Wyszukiwanie         |          | X          |
| Data obowiązywania                        | Tylko data      |          | X          |
| Zdarzenie                                 | Wyszukiwanie         | X        | X          |
| Kurs wymiany                         | Liczba dziesiętna |          | X          |
| Data ważności                       | Tylko data      |          | X          |
| Numer wiersza                           | Liczba dziesiętna |          | X          |
| Częstotliwość wypłat                         | Wyszukiwanie         | X        | X          |
| Stawka płacy                              | Waluta       |          | X          |
| Stawka płacy (podstawa)                       | Waluta       |          | X          |
| Plan                                  | Wyszukiwanie         | X        | X          |
| Pozycja                              | Wyszukiwanie         | X        | X          |
| Typ procesu                          | Zestaw opcji     | X        | X          |
| Wiersze konfiguracji punktów odniesienia            | Wyszukiwanie         |          | X          |
| Pracownik                                | Wyszukiwanie         | X        | X          |
| Numer stałego wynagrodzenia pracownika      | Tekst           | X        | X          |

**Numer dokumentu identyfikacyjnego pracownika**

| Pola                 | Typ danych   | Potrzebne | Z możliwością wyszukiwania |
|------------------------|-------------|----------|------------|
| Opis            | Tekst        |          | X          |
| Typ wpisu             | Tekst        |          | X          |
| Data ważności        | Tylko data   |          | X          |
| Numer identyfikacyjny  | Tekst        | X        | X          |
| Typ identyfikacji    | Wyszukiwanie      | X        | X          |
| Główne             | Dwie opcje |          | X          |
| Data wystawienia             | Tylko data   |          | X          |
| Agencja wystawiająca         | Wyszukiwanie      | X        | X          |
| Pracownik                 | Wyszukiwanie      | X        | X          |


## <a name="position-entities"></a>Jednostki dotyczące stanowiska

**Stanowisko funkcji**

| **Pola**               | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|--------------------------|----------------|--------------|----------------|
| Aktywacja               | Data i godzina  |              | X              |
| Dostępne do przypisania | Data i godzina  |              | X              |
| Dział               | Wyszukiwanie         |              | X              |
| Opis              | Tekst           |              | X              |
| W przeliczeniu na pełen etat     | Liczba dziesiętna |              | X              |
| Zadanie                      | Wyszukiwanie         | X            | X              |
| Numer stanowiska funkcji      | Tekst           | X            | X              |
| Nadrzędne stanowisko funkcji      | Wyszukiwanie         |              | X              |
| Typ stanowiska            | Wyszukiwanie         |              | X              |
| Emerytura               | Data i godzina  |              | X              |
| Nazwa                    | Zestaw opcji     |              | X              |
| Początek ważności               | Data i godzina  | X            | X              |
| Koniec ważności                 | Data i godzina  |              | X              |


**Typ stanowiska**

| **Pola**         | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|--------------------|---------------|--------------|----------------|
| Klasyfikacja     | Zestaw opcji    |              | X              |
| Opis        | Tekst          |              | X              |
| Nazwa typu stanowiska | Tekst          | X            | X              |


**Przypisanie pracownika do stanowiska**

| **Pola**                        | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------------------|---------------|--------------|----------------|
| Stanowisko funkcji                      | Wyszukiwanie        | X            | X              |
| Numer przypisania pracownika do stanowiska | Tekst          | X            | X              |
| Początek ważności                        | Tekst          | X            | X              |
| Koniec ważności                          |               |              | X              |
| Pracownik                            |               | X            | X              |

## <a name="job-entities"></a>Jednostki dotyczące funkcji

**Zadanie**

| **Pola**                   | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|------------------------------|----------------|--------------|----------------|
| Zezwalaj na nieograniczoną liczbę stanowisk    | Dwie opcje    |              | X              |
| Domyślnie w przeliczeniu na pełen etat | Liczba dziesiętna |              | X              |
| Opis                  | Tekst           |              | X              |
| Opis funkcji              | Tekst           |              | X              |
| Czynności związane z funkcją                 | Wyszukiwanie         |              | X              |
| Typ funkcji                     | Wyszukiwanie         |              | X              |
| Maksymalna liczba stanowisk  | Liczba całkowita   |              | X              |
| Nazwisko                         | Tekst           | X            | X              |
| Nazwa                        | Zestaw opcji     |              | X              |
| Początek ważności                   | Data i godzina  | X            | X              |
| Koniec ważności                     | Data i godzina  |              | X              |


**Funkcja stanowiska**

| **Pola**        | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------------|---------------|--------------|----------------|
| Opis       | Tekst          | X            | X              |
| Nazwa funkcji stanowiska | Tekst          | X            | X              |


**Typ zadania**

| **Pola**    | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|---------------|---------------|--------------|----------------|
| Opis   | Tekst          | X            | X              |
| Stan zwolnienia | Zestaw opcji    | X            | X              |
| Nazwa typu funkcji | Tekst          | X            | X              |

## <a name="leave-and-absence-entities"></a>Jednostki dotyczące urlopów i nieobecności

**Rejestracja urlopów**

| **Pola**            | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------|---------------|--------------|----------------|
| Podstawa daty naliczania    | Tylko data     | X            | X              |
| Data rozpoczęcia naliczania    | Tylko data     | X            | X              |
| Data niestandardowa           | Tylko data     | X            | X              |
| Naliczanie zawieszone  | Dwie opcje   |              | X              |
| Numer rejestracji urlopu | Tekst          | X            | X              |
| Plan urlopów            | Wyszukiwanie        | X            | X              |
| Data rozpoczęcia            | Tylko data     | X            | X              |
| Podstawa warstwy            | Zestaw opcji    | X            | X              |
| Pracownik                | Wyszukiwanie        | X            | X              |


**Transakcja banku urlopów**

| **Pola**                    | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------------------------|----------------|--------------|----------------|
| Liczba dni                        | Liczba dziesiętna | X            | X              |
| Firma                       | Wyszukiwanie         | X            | X              |
| Numer transakcji banku urlopów | Tekst           | X            | X              |
| Plan urlopów                    | Wyszukiwanie         |              | X              |
| Typ urlopu                    | Wyszukiwanie         | X            | X              |
| Data transakcji              | Tylko data      | X            | X              |
| Numer transakcji            | Liczba dziesiętna | X            | X              |
| Typ transakcji              | Zestaw opcji     | X            | X              |
| Pracownik                        | Wyszukiwanie         | X            | X              |


**Plan urlopów**

| **Pola**        | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------------|---------------|--------------|----------------|
| Częstotliwość naliczania | Zestaw opcji    | X            | X              |
| Firma           | Wyszukiwanie        | X            | X              |
| Opis       | Tekst          |              | X              |
| Typ urlopu        | Wyszukiwanie        | X            | X              |
| Nazwisko              | Tekst          | X            | X              |
| Data rozpoczęcia        | Tylko data     | X            | X              |


**Wniosek urlopowy**

| **Pola**           | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|----------------------|---------------|--------------|----------------|
| Komentarz              | Tekst          | X            | X              |
| Firma              | Wyszukiwanie        | X            | X              |
| Numer wniosku urlopowego | Tekst          |              | X              |
| Data żądania         | Data i godzina | X            | X              |
| Stan               | Zestaw opcji    | X            | X              |
| Pracownik               | Wyszukiwanie        | X            | X              |


**Pozycja wniosku urlopowego**

| **Pola**                  | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------------|----------------|--------------|----------------|
| Liczba dni                      | Liczba dziesiętna | X            | X              |
| Data urlopu                  | Data i godzina  | X            | X              |
| Wniosek urlopowy               | Wyszukiwanie         | X            | X              |
| Numer pozycji wniosku urlopowego | Tekst           | X            | X              |
| Typ urlopu                  | Wyszukiwanie         | X            | X              |


**Typ urlopu**

| **Pola**      | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------|---------------|--------------|----------------|
| Firma         | Wyszukiwanie        | X            | X              |
| Opis     | Tekst          |              | X              |
| Kod zarobków    | Wyszukiwanie        |              | X              |
| Nazwa typu urlopu | Tekst          | X            | X              |


**Kalendarz pracy**

| **Pola**  | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------|---------------|--------------|----------------|
| Firma     | Wyszukiwanie        | X            | X              |
| Opis | Tekst          |              | X              |
| Nazwisko        | Tekst          | X            | X              |


**Dzień w kalendarzu roboczym**

| **Pola**               | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|--------------------------|---------------|--------------|----------------|
| Data kalendarzowa            | Tylko data     | X            | X              |
| Firma                  | Wyszukiwanie        |              | X              |
| Stan                   | Tekst          |              | X              |
| Kalendarz pracy            | Wyszukiwanie        | X            | X              |
| Numer dnia w kalendarzu roboczym | Tekst          | X            | X              |


**Święto w kalendarzu roboczym**

| **Pola**  | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------|---------------|--------------|----------------|
| Nazwisko        | Tekst          |              | X              |
| Opis | Tekst          | X            | X              |


**Wiersz święta w kalendarzu roboczym**

| **Pola**                        | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------------------|---------------|--------------|----------------|
| Data święta                      | Tylko data     | X            | X              |
| Nazwisko                              | Tekst          |              | X              |
| Święto w kalendarzu pracy             | Wyszukiwanie        | X            | X              |
| Numer wiersza święta w kalendarzu roboczym | Tekst          | X            | X              |


**Zakres czasu w kalendarzu roboczym**

| **Pola**                         | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|------------------------------------|---------------|--------------|----------------|
| Firma                            | Wyszukiwanie        |              | X              |
| Godzina zakończenia                           | Liczba całkowita  |              | X              |
| Godzina rozpoczęcia                         | Liczba całkowita  |              | X              |
| Kalendarz pracy                      | Wyszukiwanie        | X            | X              |
| Dzień w kalendarzu roboczym                  | Wyszukiwanie        | X            | X              |
| Numer zakresu czasu w kalendarzu roboczym | Tekst          | X            | X              |

## <a name="organization-entities"></a>Jednostki dotyczące organizacji

**Firma**

| **Pola**   | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|--------------|---------------|--------------|----------------|
| Kod firmy | Tekst          | X            | X              |
| Nazwisko         | Tekst          | X            | X              |


**Dział**

| **Pola**        | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------------|---------------|--------------|----------------|
| Numer działu | Tekst          | X            | X              |
| Opis       | Tekst          |              | X              |
| Nazwisko              | Tekst          | X            | X              |
| Dział nadrzędny | Wyszukiwanie        |              | X              |


**Waluta**

| **Pola**         | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|--------------------|----------------|--------------|----------------|
| Kod waluty      | Tekst           | X            | X              |
| Nazwa waluty      | Tekst           | X            | X              |
| Dokładność waluty | Liczba całkowita   | X            | X              |
| Symbol waluty    | Tekst           | X            | X              |
| Obraz jednostki       | Wizerunek          |              |                |
| Kurs wymiany      | Liczba dziesiętna | X            | X              |
| Organizacja       | Wyszukiwanie         | X            | X              |
| Stan             | Zestaw opcji     |              | X              |

## <a name="payroll-entities"></a>Jednostki dotyczące listy płac

**Cykl płac**

| **Pola**  | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------|---------------|--------------|----------------|
| Opis | Tekst          | X            | X              |
| Częstotliwość   | Zestaw opcji    | X            | X              |
| Nazwisko        | Tekst          | X            | X              |


**Okres płac**

| **Pola**           | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|----------------------|---------------|--------------|----------------|
| Domyślna data płatności | Tylko data     |              | X              |
| Opis          | Tekst          |              | X              |
| Cykl płac            | Wyszukiwanie          | X            | X              |
| Numer okresu płac    | Tekst          | X            | X              |
| Data zakończenia okresu      | Tylko data     | X            | X              |
| Data rozpoczęcia okresu    | Tylko data     | X            | X              |
| Stan               | Zestaw opcji    |              | X              |


**Kody zarobków dla listy płac**

| **Pola**              | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------------------|---------------|--------------|----------------|
| Opis             | Tekst          | X            | X              |
| Uwzględnij w typie płatności | Zestaw opcji    | X            | X              |
| Płatne           | Dwie opcje   | X            | X              |
| Nazwisko                    | Tekst          |              | X              |
| Jednostka ilości           | Zestaw opcji    |              | X              |
| Śledzenie godzin FMLA        | Dwie opcje   |              | X              |


**Region podatkowy**

| **Pola**        | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------------|---------------|--------------|----------------|
| Miejscowość              | Tekst          |              | X              |
| Kraj lub region | Tekst          |              | X              |
| Powiat            | Tekst          |              | X              |
| Nazwisko              | Tekst          | X            | X              |
| Województwo | Tekst          |              | X              |


**Częstotliwość obliczania okresu płac dla świadczeń**

| **Pola**                                      | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------------------------------------------|---------------|--------------|----------------|
| Częstotliwość obliczania świadczeń                   | Wyszukiwanie        | X            | X              |
| Numer częstotliwości obliczania okresu płac dla świadczeń | Tekst          | X            | X              |
| Okres kalkulacji płac                                      | Wyszukiwanie        | X            | X              |


**Wypłata na konto bankowe**

| **Pola**                       | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|----------------------------------|----------------|--------------|----------------|
| Liczba dni                           | Waluta       |              | X              |
| Kwota (podstawa)                    | Waluta       |              | X              |
| Konto bankowe                     | Wyszukiwanie         | X            | X              |
| Numer wypłaty na konto bankowe | Tekst           | X            | X              |
| Firma                          | Wyszukiwanie         | X            | X              |
| Waluta                         | Wyszukiwanie         |              | X              |
| Kurs wymiany                    | Liczba dziesiętna |              | X              |
| Reszta                     | Dwie opcje    |              | X              |
| Priorytet                         | Liczba całkowita   |              | X              |

**Agencja wystawiająca dokument identyfikacyjny danej osoby**

| **Pola**           | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|----------------------|---------------|--------------|----------------|
| Opis adresu  | Tekst          |              | X              |
| Wiersz adresu 1       | Tekst          |              | X              |
| Wiersz adresu 2       | Tekst          |              | X              |
| Wiersz adresu 3       | Tekst          |              | X              |
| Miejscowość                 | Tekst          |              | X              |
| Kraj lub region    | Zestaw opcji    |              | X              |
| Powiat               | Tekst          |              | X              |
| Opis          | Tekst          |              | X              |
| E-mail                | Tekst          |              | X              |
| Wewnętrzny            | Tekst          |              | X              |
| Faks                  | Tekst          |              | X              |
| Nazwa agencji wystawiającej  | Tekst          | X            | X              |
| Telefon komórkowy         | Tekst          |              | X              |
| Strona                 | Tekst          |              | X              |
| Kod pocztowy          | Tekst          |              | X              |
| Skrzynka pocztowa      | Tekst          |              | X              |
| SMS                  | Tekst          |              | X              |
| Województwo    | Tekst          |              | X              |
| Telefon            | Tekst          |              | X              |
| Teleks                | Tekst          |              | X              |
| Adres URL witryny sieci Web          | Tekst          |              | X              |

**Typ dokumentu identyfikacyjnego pracownika**

| **Pola**                        | **Typ danych**  | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------------------|----------------|--------------|----------------|
| Dozwolone wartości                    | Zestaw opcji     |              | X              |
| Kraj lub region                 | Tekst           |              | X              |
| Opis                       | Tekst           |              | X              |
| Stała długość                      | Liczba całkowita   |              | X              |
| Format numeru identyfikacyjnego      | Tekst           |              | X              |
| Typ                              | Zestaw opcji     |              | X              |
| Typ dokumentu identyfikacyjnego pracownika | Tekst           | X            | X              |

## <a name="fixed-compensation-entities"></a>Jednostki dotyczące stałego wynagrodzenia

**System stałych wynagrodzeń**

| **Pola**                  | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------------|---------------|--------------|----------------|
| Firma                     | Wyszukiwanie        | X            | X              |
| Siatka wynagrodzeń           | Wyszukiwanie        |              | X              |
| Waluta                    | Wyszukiwanie        | X            | X              |
| Opis                 | Tekst          | X            | X              |
| Data obowiązywania              | Tylko data     | X            | X              |
| Data ważności             | Tylko data     | X            | X              |
| Reguła zatrudnienia                   | Zestaw opcji    | X            | X              |
| Nazwisko                        | Tekst          | X            | X              |
| Tolerancja wyjścia poza zakres      | Zestaw opcji    | X            | X              |
| Częstotliwość wypłat               | Wyszukiwanie        | X            | X              |
| Rekomendacje dozwolone      | Dwie opcje   | X            | X              |
| Konfiguracja linii punktów odniesienia  | Wyszukiwanie        |              | X              |
| Typ                        | Zestaw opcji    | X            | X              |

**Siatka wynagrodzeń**

| **Pola**                  | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------------|---------------|--------------|----------------|
| Firma                     | Wyszukiwanie        | X            | X              |
| Waluta                    | Wyszukiwanie        |              | X              |
| Opis                 | Tekst          | X            | X              |
| Data obowiązywania              | Tylko data     |              | X              |
| Data ważności             | Tylko data     |              | X              |
| Nazwisko                        | Tekst          | X            | X              |
| Konfiguracja punktów odniesienia       | Wyszukiwanie        | X            | X              |
| Typ                        | Zestaw opcji    | X            | X              |

**Poziom wynagrodzeń**

| **Pola**      | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------|---------------|--------------|----------------|
| Opis     | Tekst          |              | X              |
| Nazwisko            | Tekst          | X            | X              |
| Typ            | Zestaw opcji     | X            | X              |

**Wynagrodzenie — częstotliwość wypłat**

| **Pola**                  | **Typ danych**   | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------------|-----------------|--------------|----------------|
| Roczny współczynnik konwersji    | Liczba dziesiętna  |              | X              |
| Firma                     | Wyszukiwanie          | X            | X              |
| Opis                 | Tekst            |              | X              |
| Godzinowy współczynnik konwersji    | Liczba dziesiętna  |              | X              |
| Miesięczny współczynnik konwersji   | Liczba dziesiętna  |              | X              |
| Nazwisko                        | Tekst            | X            | X              |
| Okres                      | Zestaw opcji      |              | X              |
| Tygodniowy współczynnik konwersji    | Zestaw opcji      |              | X              |


**Ustawianie punktów odniesienia kompensacji**

| **Pola**          | **Typ danych**   | **Wymagana** | **Z możliwością wyszukiwania** |
|---------------------|-----------------|--------------|----------------|
| Firma             | Wyszukiwanie          | X            | X              |
| Typ wynagrodzenia   | Zestaw opcji      | X            | X              |
| Opis         | Tekst            | X            | X              |
| Nazwisko                | Tekst            | X            | X              |

**Wiersz ustawień punktów odniesienia wynagrodzenia**

| **Pola**            | **Typ danych**   | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------|-----------------|--------------|----------------|
| Firma               | Wyszukiwanie          | X            | X              |
| Opis           | Tekst            | X            | X              |
| Numer wiersza           | Liczba dziesiętna  | X            | X              |
| Nazwisko                  | Tekst            | X            | X              |
| Konfiguracja punktów odniesienia | Wyszukiwanie          | X            | X              |

**Region wynagrodzenia**

| **Pola**      | **Typ danych** | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------|---------------|--------------|----------------|
| Opis     | Tekst          | X            | X              |
| Nazwisko            | Tekst          | X            | X              |

**Struktura wynagrodzeń**

| **Pola**                    | **Typ danych**   | **Wymagana** | **Z możliwością wyszukiwania** |
|-------------------------------|---------------  |--------------|----------------|
| Liczba dni                        | Waluta        |              | X              |
| Podstawa kwoty                   | Waluta        |              | X              |
| Firma                       | Wyszukiwanie          | X            | X              |
| Numer struktury wynagrodzeń | Tekst            | X            | X              |
| Waluta                      | Wyszukiwanie          |              | X              |
| Kurs wymiany                 | Liczba dziesiętna  |              | X              |
| Siatka                          | Wyszukiwanie          | X            | X              |
| Poziom                         | Wyszukiwanie          | X            | X              |
| Punkt odniesienia               | Wyszukiwanie          | X            | X              |
| Konfiguracja linii punktów odniesienia    | Wyszukiwanie          | X            | X              |

**Wydarzenia stałych kompensacji**

| **Pola**            | **Typ danych**   | **Wymagana** | **Z możliwością wyszukiwania** |
|-----------------------|-----------------|--------------|----------------|
| Firma               | Wyszukiwanie          | X            | X              |
| Opis           | Tekst            | X            | X              |
| Typ zdarzenia            | Zestaw opcji      | X            | X              |
| Jest aktywne             | Dwie opcje     | X            |                |
| Nazwisko                  | Tekst            | X            | X              |

## <a name="entity-relationship-models"></a>Modele relacji między jednostkami

### <a name="worker"></a>Pracownik
![Pracownik](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Stanowisko i stanowisko funkcji
![Stanowisko i stanowisko funkcji](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Świadczenia
![Świadczenia](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Kompensacja
![Kompensacja](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Opuść
![Opuść](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Kalendarz pracy
![Kalendarz pracy](./media/HCMCommon-work-calendar-entity-diagram.png)
