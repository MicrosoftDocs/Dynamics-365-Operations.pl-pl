---
title: Zasady redukcji rabatów
description: W tym temacie opisano sposób konfigurowania zasad redukcji. Zasady redukcji sterują zachowaniem w przypadku, gdy wiele rabatów dotyczy tego samego towaru lub transakcji.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: a0cde0c22b69e7605708a647d47530840ce823b1
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270940"
---
# <a name="rebate-reduction-principles"></a>Zasady redukcji rabatów

[!include [banner](../includes/banner.md)]

Transakcje zarządzania rabatami można grupować w *zasady redukcji*, aby redukować inne rezerwy skojarzone z towarem i/lub zmniejszać wynikowe wartości obliczeń rabatów. Po skonfigurowaniu zasad redukcji rabatów można je opcjonalnie przypisać do wierszy umów dotyczących zarządzania rabatami.

Reguły te mają zastosowanie tylko w przypadku, gdy umowy rabatowe nakładają się. W związku z tym mogą udzielać wielu rabatów w sytuacji, gdy nie jest winnych wiele rabatów.

## <a name="manage-rebate-reduction-principles"></a>Zarządzaj zasadami redukcji rabatów

Aby pracować z zasadami redukcji rabatów, przejdź do ustawień zasad dotyczących redukcji rabatów **\>w zarządzaniu \>** rabatami. Następnie użyj przycisków w okienku akcji, aby dodać i usunąć zasady redukcji zgodnie z wymaganiami. W każdym nowej zasadzie ustaw pola zgodnie z opisem w poniższej tabeli.

| Pole | opis |
|---|---|
| Zasada redukcji rabatów | Służy do wprowadzania unikatowej nazwy zasady redukcji rabatów. |
| opis | Służy do wprowadzania opisu zasady redukcji rabatów. |
| Zastosuj zmniejszenie | Zaznaczenie tego pola wyboru umożliwia zastosowanie podstawy redukcji do rabatów należących do tej reguły redukcji rabatów. |
| Podstawy redukcji | Jeśli zaznaczono pole wyboru **Zastosuj redukcję**, wybierz podstawę redukcji (*Warunki*, *Rabaty* lub *Oba*). W przypadku wybrania opcji *Oba* i w przypadku zaksięgowania zarówno zapewnienia, jak i rabatu dla poprzedniej umowy zostanie zastosowany tylko rabat. |
| Wyklucz z redukcji | Jeśli to pole wyboru jest zaznaczone, rezerwy i rabaty należące do tej reguły redukcji rabatów zostaną wykluczone z kolejnych redukcji. Ustawienie pola **Podstawa redukcji** nie ma zastosowania do tego ustawienia. |

## <a name="examples-of-rebate-reduction-principle-setups"></a>Przykłady ustawień zasady redukcji rabatów

W poniższej tabeli pokazano kilka typowych przykładów ustawień zasady redukcji rabatów. W przypadku każdej z tych zasad redukcji rabatów wartość w polu **Opis** opisuje cel zasady redukcji rabatów.

| Zasada redukcji rabatów | opis | Zastosuj zmniejszenie | Podstawy redukcji | Wyklucz z redukcji |
|---|---|---|---|---|
| Odłożone | Zmniejsz rabat | Tak | Obie | Nr |
| Bez rabatu | Wyklucz rabat | Tak | Rabat | Tak |
| Wiele | Wiele rabatów | Tak | Obie | Tak |
| None | Tylko dla rabatów i rabatów | Nr | Obie | Tak |
| Inicjowanie obsługi | Tylko prowizja | Tak | Inicjowanie obsługi | Nr |
| Rabat | Tylko rabaty | Tak | Rabat | Tak |

## <a name="examples-of-rebate-reduction-principle-calculations"></a>Przykłady ustawień zasady obliczeń redukcji rabatów

Zamówienie sprzedaży ma jeden wiersz. Ten wiersz ma wartość $1000. Do zamówienia mają zastosowanie następujące oferty:

- **Transakcja 1:** 10% na $1000
- **Transakcja 2:** 15% na $1000
- **Transakcja 3:** 20% na $1000
- **Transakcja 4:** 25% na $1000

Kolejność przetwarzania jest bardzo ważna. Podstawą przetwarzania jest sposób pracy w sposób opisany w teście [przetwarzania, przeglądu i zaksięgowania rabatów](process-review-post.md).

Na przykład w poniższej tabeli podsumowano wynik użycia zamówienia *1, 2, 3, 4*, a jeśli są przetwarzane tylko rezerwy.

| Umowa | Opis i ustawienia | Wynik prowizji |
|---|---|---|
| 1 | <p>W klasyfikacji nie są sprawdzane inne transakcje pod celu zmniejszenia. Sprawdzenie odbywa się w przypadku zarówno rezerw, jak i rabatów.</p><ul><li>**Zastosuj zmniejszenie:** *Nie*</li><li>**Podstawy redukcji:** *Obie*</li><li>**Wyklucz z redukcji:** *Nie*</li></ul> | $1000 × 10% = $100 |
| 2 | <p>W klasyfikacji są sprawdzane inne transakcje pod uwagę w redukcjach, ale są oznaczane w ten sposób, że zostały zignorowane. Sprawdzanie jest wykonywane tylko w przypadku rabatów.</p><ul><li>**Zastosuj zmniejszenie:** *Tak*</li><li>**Podstawy redukcji:** *Rabat*</li><li>**Wyklucz z redukcji:** *Tak*</li></ul> | $1000 × 15% = $150 |
| 3 | <p>W klasyfikacji są sprawdzane inne transakcje pod celu zmniejszenia. Sprawdzenie odbywa się w przypadku zarówno rezerw, jak i rabatów.</p><ul><li>**Zastosuj zmniejszenie:** *Tak*</li><li>**Podstawy redukcji:** *Obie*</li><li>**Wyklucz z redukcji:** *Nie*</li></ul> | ($1000 – Transakcja 1) × 20% = $180 |
| 4 | <p>W klasyfikacji są sprawdzane inne transakcje pod celu zmniejszenia. Sprawdzenie odbywa się w przypadku zarówno rezerw, jak i rabatów.</p><ul><li>**Zastosuj zmniejszenie:** *Tak*</li><li>**Podstawy redukcji:** *Obie*</li><li>**Wyklucz z redukcji:** *Nie*</li></ul> | (1000 USD – Transakcja 1 – Transakcja 3) × 25% = $180 |

W poniższej tabeli pokazano kilka przykładów, w których świadczenia są przetwarzane w różnych zamówieniach i w związku z tym są realizowane różne sumy. Odchylenie w rezerwach zależy od kolejności, w których system przetwarza transakcje. Bardzo ważne jest, aby zrozumieć, w jaki sposób zamówienie przetwarzania wpływa na ostateczną kwotę rabatu.

| Kolejność | Obliczenie |
|---|---|
| 1<br>(1, 2, 3, 4) | <ul><li>**Transakcja 1:** $1000 × 10% = $100</li><li>**Transakcja 2:** $1000 × 15% = $150</li><li>**Transakcja 3:** ($1000 – Transakcja 1) × 20% = $180</li><li>**Transakcja 4:** ($1000 – Transakcja 1 – Transakcja 2) × 25% = $180</li><li>**Suma prowizji:** $610</li></ul> |
| 2<br>(4, 3, 2, 1) | <ul><li>**Transakcja 4:** $1000 x 25% = $250</li><li>**Transakcja 3:** (1,000 – Transakcja 4) × 20% = $150</li><li>**Transakcja 2:** $1000 x 15% = $150</li><li>**Transakcja 1:** $1000 x 10% = $100</li><li>**Suma prowizji:** $650</li></ul> |
| 3<br>(3, 2, 1, 4) | <ul><li>**Transakcja 3:** $1000 x 20% = $200</li><li>**Transakcja 2:** $1000 x 15% = $150</li><li>**Transakcja 1:** $1000 x 10% = $100</li><li>**Transakcja 4:** (1000 USD – Transakcja 3 – Transakcja 1) × 25% = $175</li><li>**Suma prowizji:** $625</li></ul> |
| 4<br>(2, 4, 1, 3) | <ul><li>**Transakcja 2:** $1000 × 15% = $150</li><li>**Transakcja 4:** 1000 × 25% = $250</li><li>**Transakcja 1:** $1000 × 10% = $100</li><li>**Transakcja 3:** (1000 USD – Transakcja 4 – Transakcja 1) × 20% = $130</li><li>**Suma prowizji:** $630</li></ul> |
