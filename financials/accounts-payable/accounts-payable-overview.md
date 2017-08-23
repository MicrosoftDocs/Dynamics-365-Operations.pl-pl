---
title: "Konfigurowanie modułu Rozrachunki z dostawcami"
description: "Ten artykuł zawiera opis stron, które służą do konfigurowania podstawowych i opcjonalnych funkcji modułu Rozrachunki z dostawcami w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Opisano również kroki konfiguracji, które należy wykonać przed rozpoczęciem konfigurowania modułu Rozrachunki z dostawcami."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: Shiva.Pandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 45d28110ca93875eb534c69886ac2074ea4fe737
ms.openlocfilehash: 9b29fec7fadbb1ac699f1144f011df1bfd2f511a
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2017

---

# <a name="configure-accounts-payable"></a>Konfigurowanie modułu Rozrachunki z dostawcami

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera opis stron, które służą do konfigurowania podstawowych i opcjonalnych funkcji modułu Rozrachunki z dostawcami w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Opisano również kroki konfiguracji, które należy wykonać przed rozpoczęciem konfigurowania modułu Rozrachunki z dostawcami.

<a name="prerequisites-for-accounts-payable-setup"></a>Wymagania wstępne do konfiguracji modułu Rozrachunki z dostawcami
----------------------------------------

Przed skonfigurowaniem modułu Rozrachunki z dostawcami, trzeba wykonać następującą konfigurację:

-   W księdze głównej:
    -   Jeśli mają być używane arkuszy płatności, skonfiguruj arkusze płatności.
    -   Jeśli mają być uruchamiane korekty kursu wymiany, ustaw kody waluty na stronie Waluty, skonfiguruj typy kursu wymiany na stronie Typy kursu wymiany i skonfiguruj kursy wymiany walut na stronie Kursy wymiany walut.
-   W sekcji Zarządzanie gotówką i bankami skonfiguruj konta bankowe używane z metodami płatności.

## <a name="setup-pages-for-accounts-payable"></a>Strony ustawień modułu Rozrachunki z dostawcami

Poniższe strony umożliwiają konfigurowanie podstawowych funkcji rozrachunków z dostawcami dla każdej firmy. Strony są wymienione w zalecanej kolejności ustawień. Aby ułatwić proces ustawień, można tworzyć szablony na podstawie pierwszych utworzonych rekordów. W szablonie wartości są zwykle wprowadzane w wielu polach, aby odzwierciedlić funkcje, które organizacja chce zaimplementować dla określonego typu dostawcy.
1.  Na stronie Warunki płatności można definiować warunki płatności przypisywane do zamówień sprzedaży, zamówień zakupu, odbiorców i dostawców oraz określających terminy płatności faktur. Aby uzyskać więcej informacji, zobacz [Definiowanie opłat od płatności dostawcy](tasks/define-vendor-payment-fees.md).
2.  Na stronie Metody płatności — Dostawcy można tworzyć i obsługiwać informacji o tym, jak organizacja płaci swoim dostawcom.
3.  Strona Grupy dostawców umożliwia tworzenie i obsługiwanie grup dostawców, którzy mają wspólne kluczowe parametry dotyczące księgowania, rozliczania i płatności, raportowania oraz prognozowania.
4.  Strona Profile księgowania dostawców pozwala zdefiniować, jak transakcje dostawcy są księgowane w księdze głównej.
5.  Strona Parametry modułu rozrachunków z dostawcami umożliwia konfigurowanie ustawień domyślnych stosowanych w przypadku braku bardziej szczegółowego ustawienia, parametrów różnego rodzaju funkcji oraz różnych sekwencji numerów do rozrachunków z dostawcami.
6.  Strona Ustawienia formularza umożliwia definiowanie formatu różnych dokumentów związanych z dostawcami oraz używanych w firmie do śledzenia przychodów od dostawców i wprowadzania przyczyn przepływu płatności do dostawców.
7.  Strona Dostawcy umożliwia tworzenie i obsługiwanie kont dostawców, w tym urzędów skarbowych, do których organizacja przesyła deklaracje podatkowe.

## <a name="optional-setup-pages-for-accounts-payable"></a>Opcjonalne strony ustawień rozrachunków z dostawcami
Oprócz podstawowych funkcji moduł Rozrachunki z dostawcami ma inne funkcje, które można skonfigurować.

Dodatkowe strony ustawień są zorganizowane według funkcji.

**Zasady**
-   Na stronie Zasady dotyczące faktur od dostawców można ustawić zasady dotyczące faktur od dostawców.

**Uzgadnianie faktur**

-   Strona Dozwolone rozbieżności sum faktury pozwala ustawić tolerancje dla sum faktury.
-   Strona Zasady uzgadniania pozwala ustawić zasady uzgadniania dwuelementowego i trzyelementowego.
-   Strona Rozbieżności cenowe pozwala ustawić rozbieżności dla cen jednostkowych.
-   Strona Grupy rozbieżności cenowych pozycji pozwala ustawić grupy rozbieżności dla cen jednostkowych.
-   Strona Grupy rozbieżności cenowych dostawcy pozwala ustawić grupy rozbieżności dla cen dostawcy.
-   Strona Dozwolone rozbieżności opłat pozwala ustawić rozbieżności dla opłat.

**Przepływ pracy**

-   Strona Przepływy pracy dla rozrachunków z dostawcami pozwala ustawić konfiguracje przepływu pracy dla zatwierdzeń dziennika i zapotrzebowań na zakup.

**Przyczyny**

-   Strona Przyczyny dotyczące dostawcy pozwala ustawić kody przyczyn.

**Opłaty**

-   Strona Kody opłat pozwala ustawić kody dla opłat używane na zamówieniach zakupu.
-   Strona Grupa opłat dla dostawcy pozwala utworzyć i obsługiwać grupy opłat dla dostawców.
-   Strona Grupy opłaty dla towaru pozwala utworzyć i obsługiwać grupy opłat dla towarów.
-   Strona Opłaty automatyczne pozwala zdefiniować opłaty, które są automatycznie przypisywane do zamówień.

**Pozycje dodatkowe**

-   Strona Grupy towarów dodatkowych - Dostawcy pozwala utworzyć i obsługiwać grupy towarów dodatkowych dla dostawców.
-   Strona Grupy towarów dodatkowych - zapasy pozwala utworzyć i obsługiwać grupy towarów dodatkowych dla towarów.

**Dystrybucja**

-   Strona Warunki dostawy pozwala utworzyć i obsługiwać warunki dotyczące przekazywania towaru kupcowi przez sprzedającego.
-   Strona Metody dostawy pozwala umożliwia tworzenie i obsługiwanie metod transportu używanych przy dostawie zamówienia kupcowi przez sprzedającego.
-   Strona Kody przeznaczenia  umożliwia tworzenie i obsługiwanie identyfikatorów i opisów dotyczących miejsc przeznaczenia dostaw.

**Formularze**

-   Strona Notatki umożliwia tworzenie standardowego tekstu wyświetlanego na różnych stronach.
-   Strona Sortowanie formularza umożliwia konfigurowanie kolejności sortowania zapotrzebowań, list przychodów, dokumentów dostawy i faktur.
-   Strona Konfiguracja zarządzania drukowaniem  umożliwia drukowanie informacji o zarządzaniu dla oryginałów i kopii stron.

**Płatności**

-   Strona Rabaty gotówkowe umożliwia konfigurowanie warunków uzyskiwania rabatów gotówkowych i zarządzanie nimi. Kody rabatów gotówkowych są połączone z dostawcami i stosowane do zamówień zakupu.
-   Strona Harmonogramy płatności umożliwia ustawienie harmonogramów płatności, które są używane do zarządzania płatnościami rat dla dostawców.
-   Strona Dni płatności umożliwia definiowanie dni płatności, które są używane w obliczeniach terminów płatności, oraz określanie dni płatności dla określonego dnia tygodnia lub miesiąca.
-   Strona Opłata umożliwia tworzenie i obsługiwanie opłat skojarzonych z dostawcami.
-   Strona Instrukcja płatności umożliwia tworzenie i obsługiwanie instrukcji płatności.

**Statystyki**

-   Strona Definicje okresów wiekowania umożliwia konfigurowanie zdefiniowanych przez użytkownika interwałów służących do analizy rozkładu terminów płatności dla kont dostawców.
-   Strona Branża umożliwia tworzenie kodów branż (LOB) przypisanych do dostawców.

**Podatek 1099**

-   Strona **Pola 1099** umożliwia sprawdzenie i aktualizację minimalnych kwot, które należy podać do urzędu skarbowego zgodnie z najnowszymi wymaganiami.

## <a name="optional-setup-for-other-modules"></a>**Ustawienia opcjonalne dla innych modułów**
**Administrowanie organizacją**

-   Strona Sekwencja identyfikatorów umożliwia konfigurowanie grup sekwencji identyfikatorów dla numerów faktur.
-   Na poniższych stronach ustaw informacje dotyczące adresu:
    -   Ustawienia adresu
    -   Kody NAF
    -   Import kodów pocztowych

**Księga główna**

-   Strona Wymiary finansowe umożliwia konfigurowanie wymiarów finansowych.
-   Na poniższych stronach ustaw informacje dotyczące podatku:
    -   Kody podatków
    -   Grupy podatków
    -   Grupy podatków dla pozycji
    -   Grupa kont
    -   Kody zwolnienia z podatku
    -   Właściwe miejscowo urzędy skarbowe
    -   Urzędy skarbowe
    -   Okresy rozliczania podatku

**Zarządzanie gotówką i bankami**

-   Strona Kody celów płatności umożliwia ustawieni kodu celu banku centralnego.






