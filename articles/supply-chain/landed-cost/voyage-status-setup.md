---
title: Ustawienia stanu podróży
description: W tym artykule opisano sposób ustanawiania wartości stanu, które użytkownicy mogą przypisywać do podróży.
author: Weijiesa
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 1cec728f2fa49175c063818ee7f188b441945647
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907327"
---
# <a name="voyage-status-setup"></a>Ustawienia stanu podróży

[!include [banner](../../includes/banner.md)]

Na stronie **Stany podróży** ustal zestaw wartości stanów, które użytkownicy mogą przypisywać do podróży. Użytkownicy mogą przypisywać wartości statusu podróży do wszystkich poziomów podróży: rejsu, kontenera wysyłkowego, folio, zamówienia zakupu i pozycji (linie zakupu i zamówienia przeniesienia). Są one używane do dwóch celów:

- Poinformuj użytkownika o statusie podróży, kontenerze wysyłkowym, folio, zamówieniu zakupu lub pozycji (wiersze zakupu i wiersze zamówienia przeniesienia).
- Ograniczenie użycia obszaru kosztów przez zapobieganie modyfikacji lub usunięciu.

Aby skonfigurować stany podróży, przejdź do **Koszt dostawy \> Konfiguracja \> Stany podróży**. Można tam dodawać, usuwać i edytować stany za pomocą przycisków w okienku akcji.

Dla każdego obszaru kosztów jest ustawiony własny zestaw oraz hierarchia stanów podróży. Dlatego na stronie **Stany podróży**, w polu **Obszar kosztów**, należy najpierw wybrać obszar kosztów, dla którego chcesz wyświetlić lub utworzyć stany podróży. Następnie, w razie potrzeby, dla każdego stanu podróży należy ustawić pola opisane w poniższej tabeli. Zwróć uwagę, że status podróży może być również automatycznie zmieniany przez zdarzenia systemowe, takie jak reguły, które zostały ustanowione przy użyciu centrum kontroli śledzenia.

| Pole | opis |
|---|---|
| Stan podróży | Wprowadź nazwę statusu podróży. |
| opis | Wprowadź opis wybranego stanu podróży. |
| Modyfikuj | To pole wyboru należy zaznaczyć, jeśli użytkownicy mogą modyfikować podróże o tym stanie. |
| Usuwanie | Zaznacz to pole wyboru, jeśli użytkownicy mogą usuwać podróże o tym statusie. |
| Wymagany | Zaznacz to pole wyboru, aby status podróży był obowiązkowy i nie można go było pominąć. |
| Nadrzędne | To pole pozwala ustanowić hierarchię między wartościami stanu. Stany podróży można zmieniać (ręcznie lub automatycznie) tylko w dół hierarchii, z stanu nadrzędnego na jeden z jego stanów podrzędnych.

> [!NOTE]
> Należy skonfigurować tylko określone stany podróży używane przez organizację. Do typowych stanów podróży należą: *Potwierdzone*, *Towary w transporcie*, *Odebrane*, *Gotowe do wyceny* i *Wycenone*. Mogą jednak wystąpić inne stany.
