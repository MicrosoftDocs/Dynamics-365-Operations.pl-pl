---
title: Naliczanie czasu wolnego na podstawie liczby przepracowanych godzin
description: W tym temacie opisano, jak w planach urlopów można skonfigurować naliczanie czasu wolnego na podstawie liczby przepracowanych godzin.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-09-17
ms.dyn365.ops.version: ''
ms.openlocfilehash: 229ae14b9e2dedcd0ade094a772f16c0524d32a7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462259"
---
# <a name="accrue-time-off-based-on-hours-worked"></a>Naliczanie czasu wolnego na podstawie liczby przepracowanych godzin

## <a name="overview"></a>Przegląd

Organizacje rozliczające pracowników godzinowo mogą przyznawać czas wolny na podstawie liczby przepracowanych godzin, a nie stażu pracy w firmie. Informacje o liczbie przepracowanych godzin są zazwyczaj przechowywane w systemie rejestracji czasu pracy. 

## <a name="leave-plans"></a>Plany urlopów

W planie urlopów typem naliczania może być liczba miesięcy zatrudnienia lub liczba przepracowanych godzin. W przypadku wybrania opcji liczby przepracowanych godzin istnieją dwa typy godzin służące do naliczania: zwykłe i nadgodziny.

Aby ustawić używanie liczby przepracowanych godzin w planie urlopów, wykonaj następujące kroki:

1. Na stronie **Plany urlopów i nieobecności** kliknij opcję **Utwórz nowy plan**.
2. Nadaj nazwę swojemu planowi urlopów.
3. Wybierz częstotliwość naliczania w planie urlopów.
5. Wybierz datę początkową planu.
6. Wybierz podstawę okresu naliczania i w razie potrzeby określ datę specyficzną dla pracownika.
7. W harmonogramie naliczania jako typ naliczania wybierz **Przepracowane godziny**.
8. Wybierz typ godzin, jakie mają być naliczane.
9. Wprowadź liczbę przepracowanych godzin oraz powiązane z nią naliczoną kwotę, minimalne saldo i maksymalną ilość przeniesienia na następny okres lub przyznania.

Mechanizm przetwarzania naliczeń w planach opartych na liczbie przepracowanych godzin wykorzystuje częstotliwość naliczania oraz podstawę okresu naliczania do określenia liczby godzin, jaką trzeba naliczyć.

## <a name="annual-accrual-frequency"></a>Roczna częstotliwość naliczania

| Data przyznania naliczenia    | Warstwa liczby przepracowanych godzin    | Kwota naliczenia        | Daty przepracowanych godzin   | Faktycznie przepracowane godziny| Nagroda               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 01.01.2018–31.12.2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 01.01.2018–31.12.2018  | 2000                | 0                 |


## <a name="monthly-accrual-frequency"></a>Miesięczna częstotliwość naliczania

| Data przyznania naliczenia    | Warstwa liczby przepracowanych godzin    | Kwota naliczenia        | Daty przepracowanych godzin   | Faktycznie przepracowane godziny| Nagroda               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 01.08.2018–31.08.2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 01.08.2018–31.08.2018   | 184                 | 3                   |

## <a name="semi-monthly-accrual-frequency"></a>Dwutygodniowa częstotliwość naliczania

| Data przyznania naliczenia    | Warstwa liczby przepracowanych godzin    | Kwota naliczenia        | Daty przepracowanych godzin   | Faktycznie przepracowane godziny| Nagroda               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 16.08.2018–31.08.2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 16.08.2018–31.08.2018  | 75                  | 0                   |

## <a name="weekly-accrual-frequency"></a>Tygodniowa częstotliwość naliczania

| Data przyznania naliczenia    | Warstwa liczby przepracowanych godzin    | Kwota naliczenia        | Daty przepracowanych godzin   | Faktycznie przepracowane godziny| Nagroda               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 27.08.2018–31.08.2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 27.08.2018–31.08.2018  | 35                  | 0                   |

## <a name="employee-assigned-leave-plans"></a>Przypisane plany urlopów przypisane do pracownika

W planach urlopów przypisanych do pracownika są wyświetlane podstawa warstwy i typ godzin dla planów, w których jako typ naliczania zdefiniowano liczbę przepracowanych godzin. Dla aktywnych planów jako informacja pomocnicza jest również wyświetlana rzeczywista liczba przepracowanych godzin w okresach naliczania według stanu na bieżący dzień. 

## <a name="loading-data"></a>Trwa ładowanie danych

Faktycznie przepracowane godziny można zaimportować za pomocą jednostki Godziny przepracowane do podstawy urlopu i nieobecności dostępnej w module Zarządzanie danymi. Jeśli są używane kalendarze czasu pracy, aparat importu sprawdzi, czy liczba zwykłych przepracowanych godzin nie przekracza liczby godzin określonej w dziennym harmonogramie w kalendarzu. Ponadto aparat importu sprawdzi, czy liczba godzin przepracowanych w danym dniu nie przekracza 24. 

Następujące informacje są potrzebne w celu zaimportowania liczby faktycznie przepracowanych godzin do wykorzystania w procesie naliczania urlopu:

+ Numer pracownika 
+ Data dnia pracy
+ Typ
+ Godziny

Z jedną datą może być skojarzony tylko jeden element każdego typu.

| NUMER PRACOWNIKA       | DATA DNIA PRACY           | TYP                  | LICZBA GODZIN                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Normalna               | 8                    |       
| 000337                | 8/7/2018             | Normalna               | 8                    |
| 000337                | 8/7/2018             | Nadgodziny              | 3                    |
| 000337                | 8/8/2018             | Normalna               | 8                    |
| 000337                | 8/7/2018             | Normalna               | 8                    |
| 000337                | 8/9/2018             | Normalna               | 8                    |
