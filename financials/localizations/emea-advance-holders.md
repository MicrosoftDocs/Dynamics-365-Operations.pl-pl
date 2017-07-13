---
title: Posiadacze zaliczek
description: "Ten temat zawiera więcej informacji o funkcjonalności posiadacza zaliczki w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 262574
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: fedcd2b4756faddc20fe6f304e4448949acdaa61
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Posiadacze zaliczek
<a id="advance-holders" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Ten temat zawiera więcej informacji o funkcjonalności posiadacza zaliczki w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

*Posiadacz zaliczki* to pracownik firmy, który odpowiada za kwotę wydatku pokrytą przez organizację. Posiadaczem zaliczki może być tylko pracownik firmy. Gdy następuje zaopatrzenie, posiadacz zaliczki informuje firmę o dokonanych wydatkach. Wtedy firma zwraca pracownikowi wydatkowaną kwotę. Firma kontroluje salda wszystkich posiadaczy zaliczek. Użytkownicy w firmach w Estonii, na Łotwie, Litwie, w Polsce, Czechach, na Węgrzech i w Rosji mogą wykazywać konkretne transakcje towarzyszące operacjom z udziałem pracowników firmy odpowiedzialnych za kwoty wydatków pokrywane przez organizację.

## Konfigurowanie posiadacza zaliczki
<a id="set-up-an-advance-holder" class="xliff"></a>
Aby skonfigurować posiadacza zaliczki, należy kolejno wykonać następujące zadania:
1.  Tworzenie grup posiadaczy zaliczek.
2.  Konfigurowanie profilu księgowania pracownika.
3.  Konfigurowanie parametrów modułu Rozrachunki z dostawcami.
4.  Tworzenie szczegółowych warunków płatności dla posiadacza zaliczki.
5.  Tworzenie posiadacza zaliczki.

### Grupy posiadaczy zaliczek
<a id="advance-holder-groups" class="xliff"></a>

Użyj strony **Grupy posiadaczy zaliczek**, aby utworzyć grupę posiadaczy zaliczek. Można określić nazwę, opis i konto przeciwstawne dla grupy posiadaczy zaliczek.
### Profil księgowania pracownika
<a id="employee-posting-profile" class="xliff"></a>

Użyj strony **Profile księgowania pracowników**, aby utworzyć profil dla transakcji posiadaczy zaliczek. W profilu księgowania pracownika można podać następujące informacje:
|Pole |opis|
|------|-----------|
|Profil księgowania|Wprowadź kod identyfikacyjny profilu księgowania dla posiadacza zaliczki.|
|opis|Wprowadź krótki opis profilu księgowania.|
|Ważny dla|Wybierz jedną z następujących opcji poziomu grupowania dla konfiguracji profilu księgowania: 
**Tabela** — Ta opcja służy do konfigurowania profilu księgowania dla jednego posiadacza zaliczki. Należy podać kod posiadacza zaliczki w polu Odwołanie.
**Grupa** — Ta opcja służy do konfigurowania profilu księgowania dla grupy posiadaczy zaliczek. Należy podać kod grupy w polu Odwołanie.
**Wszystko** — Ta opcja służy do konfigurowania profilu księgowania dla wszystkich posiadaczy zaliczek. | |Odwołanie| Wybierz kod posiadacza zaliczki, jeśli w polu Ważny dla została wybrana opcja Tabela, lub grupę posiadaczy zaliczek, jeśli w polu Ważny dla zaznaczono opcję Grupa. | |Konto rozrachunkowe| Wybierz konto rozrachunkowe do księgowania transakcji.|



### Parametry modułu rozrachunków z dostawcami
<a id="account-payable-parameters" class="xliff"></a>

Aby wykazywać transakcje posiadaczy zaliczek, należy skonfigurować następujące informacje na stronie **Parametry modułu rozrachunków z dostawcami** w sekcji **Posiadacze zaliczek**.
|                                                |                   |
|------------------------------------------------|-------------------|
|  **Pole**                                     | **Opis**                                                                                                                                                                  |
| **Profil księgowania**                            | Wybierz domyślny profil do realizowania transakcji posiadaczy zaliczek.                                                                                                         |
| **Sortowanie posiadaczy zaliczek**                     | Jeśli zaznaczysz tę opcję, posiadacze zaliczek będą wyświetlani na początku listy na stronie **Posiadacze zaliczek**.                                                                     |
| **Rozchody przy otwartym saldzie**                 | Jeśli zaznaczysz tę opcję, będzie dozwolone wydanie zaliczki gotówkowej posiadaczowi zaliczki mającemu otwarte saldo dodatnie.                                                                      |
| **Zamykanie salda za pośrednictwem kasy** | Wybierz kod arkusza dokumentu kasowego. Ten kod arkusza jest używany do generowania dokumentów KW i KP podczas zamykania sald posiadacza zaliczki za pośrednictwem kasy. |
| **Kasa**                                       | Wybierz konto kasowe, które będzie decydowało o załącznikach używanych do zamykania sald posiadacza zaliczki.                                                                 |
| **Zamykanie salda za pośrednictwem banku** | Wybierz kod arkusza transakcji, który będzie używany do zamykania sald za pośrednictwem banku.                                                                                                   |
| **Typ konta**                               | Wybierz bank, który będzie używany do zamykania sald posiadacza zaliczki za pośrednictwem banku.                                                                                                        |
| **Konto główne**                               | Wybierz kod konta bankowego, który będzie używany do zamykania sald posiadacza zaliczki za pośrednictwem banku.                                                                                           |

### Warunki płatności dla posiadacza zaliczki
<a id="terms-of-payment-for-advance-holder" class="xliff"></a>

Aby poprawnie zarejestrować i zaksięgować zamówienie zakupu w kontekście posiadacza zaliczki, należy użyć warunków płatności skonfigurowanych z opcją **Od posiadacza zaliczki** ustawioną na wartość **Prawda**.
### Tworzenie posiadacza zaliczki
<a id="create-an-advance-holder-creation" class="xliff"></a>

Przed utworzeniem posiadacza zaliczki muszą już istnieć skonfigurowani pracownicy. Aby uzyskać więcej informacji, zobacz [Wprowadzanie informacji o pracowniku (przewodnik po zadaniu).](http://ax.help.dynamics.com/en/wiki/enter-worker-information/) Użyj strony **Posiadacze zaliczek**, aby skonfigurować pracownika jako posiadacza zaliczki. Wybierz pracownika, który ma być posiadaczem zaliczki, kliknij przycisk **Edytuj**, a następnie ustaw w opcji **Posiadacz zaliczki** wartość **Prawda**. Trzeba również wypełnić następujące pola:
|                |                                                                                             |
|----------------|---------------------------------------------------------------------------------------------|
| **Pole**      | **Opis**                                                                             |
| **Grupa**      | Wybierz grupę posiadaczy zaliczek.                                                             |
| **Seria**     | Wprowadź serię dokumentu używanego do weryfikacji tożsamości posiadacza zaliczki. |
| **Numer**     | Wprowadź numer dokumentu używanego do weryfikacji tożsamości posiadacza zaliczki. |
| **Data wystawienia** | Wybierz lub wprowadź datę wydania dokumentu.                                                    |
| **Wystawione przez**  | Wprowadź dane organu lub osoby, która wydała dokument.                       |

## Zapytania i raporty dotyczące posiadaczy zaliczek
<a id="advance-holder-inquiries-and-reports" class="xliff"></a>
### Zapytania o transakcje posiadaczy zaliczek
<a id="advance-holder-transactions-inquiry" class="xliff"></a>

Aby uzyskać listę transakcji posiadacza zaliczki, kliknij przycisk **Transakcje** znajdujący się na stronie **Posiadacze zaliczek**. Aby wyświetlić transakcje wszystkich posiadaczy zaliczek lub utworzyć szczegółowe zapytanie dotyczące transakcji posiadaczy zaliczek, wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Zapytania i raporty** &gt; **Zapytania i raporty posiadaczy zaliczek** &gt; Transakcje. Kliknij opcję **Załącznik**, a zostanie otwarta strona **Transakcje na załączniku**.
### Zapytania o salda posiadaczy zaliczek
<a id="advance-holder-balance-inquiry" class="xliff"></a>

Aby zobaczyć saldo posiadacza zaliczki, użyj strony **Posiadacze zaliczek**. Aby wyświetlić salda wszystkich posiadaczy zaliczek lub utworzyć szczegółowe zapytanie dotyczące kont posiadaczy zaliczek, wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Zapytania i raporty** &gt; **Zapytania i raporty posiadaczy zaliczek** &gt; **Saldo**.
### Raport salda posiadacza zaliczki
<a id="advance-holder-balance-report" class="xliff"></a>

Aby wyświetlić podgląd i wydrukować raport oparty na informacjach o saldach posiadaczy zaliczek, wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Zapytania i raporty** &gt; **Zapytania i raporty posiadaczy zaliczek** &gt; **Raport salda posiadacza zaliczki**.
### Raport transakcji posiadacza zaliczki
<a id="advance-holder-transactions-report" class="xliff"></a>

Aby wyświetlić podgląd i wydrukować raport oparty na transakcjach posiadaczy zaliczek, wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Zapytania i raporty** &gt; **Zapytania i raporty posiadaczy zaliczek** &gt; **Raport transakcji posiadacza zaliczki**.



Informacje dodatkowe
<a id="see-also" class="xliff"></a>
--------

[Transakcje posiadacza zaliczki](emea-advance-holders-transactions.md)




