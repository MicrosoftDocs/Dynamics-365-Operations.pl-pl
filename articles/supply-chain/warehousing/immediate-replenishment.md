---
title: Natychmiastowe uzupełnianie zapasów
description: W tym temacie opisano, jak wykorzystywać funkcję natychmiastowego uzupełniania zapasów do uzupełnienia zapasów, gdy dyrektywa lokalizacji nie alokuje zapasów.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSReplenishmentTemplates
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 6e2919c003d1dc67b988345260b2747364752222
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004784"
---
# <a name="immediate-replenishment"></a>Natychmiastowe uzupełnianie zapasów

[!include [banner](../includes/banner.md)]

Funkcja natychmiastowego uzupełniania zapasów pozwala błyskawicznie uzupełnić zapasy, gdy wiersz dyrektywy lokalizacji nie jest w stanie przydzielić zapasów. Uzupełnienie zapasów opiera się na jednym wierszu w konfiguracji dyrektywy lokalizacji. Jeśli zapasy nie są dostępne w jednostce miary określonej za pomocą tego wiersza, uzupełnienie zapasów w tej jednostce miary odbywa się natychmiast.

Natychmiastowe uzupełnianie zapasów jest alternatywą dla metody, w której alokacja zapasów bazuje na większej liczbie wierszy w dyrektywie lokalizacji, a popyt jest sumowany na koniec alokacji i uzupełniany w jednostce miary określonej przez ostatni wiersz w dyrektywie lokalizacji.

Zaletami używania natychmiastowego uzupełnienia zapasów jest to, że uzupełnianie może być ograniczone przez określone jednostki, a ilość można skierować do określonej lokalizacji.

## <a name="business-scenario"></a>Scenariusz biznesowy

Na przykład masz magazyn, który ma oddzielne obszary pobrania dla jednostek miary „pudełko” i „sztuka”. Chcesz zoptymalizować proces pobierania, tak aby była pobierana maksymalna możliwa liczba pudełek, a następnie brakująca ilość mniejsza niż zawartość pudełka była dobierana z obszaru „sztuka”.

W takim przypadku można użyć funkcji natychmiastowego uzupełniania zapasów. W dyrektywie lokalizacji można skonfigurować natychmiastowe uzupełnienie zapasów pudełkami, tak aby uzupełnienie zapasów popytu ładunku następowało natychmiast po wystąpieniu niedoboru pudełek, które można pobrać dla ilości popytu. W ten sposób optymalizujesz proces pobierania, ponieważ zostanie pobrana maksymalna możliwa liczba pudełek. Funkcja natychmiastowego uzupełniania zapasów spowoduje uzupełnienie pudełkami, a popyt nie zostanie przekazany dalej w celu pobrania ilości w jednostce miary „sztuka”. Innymi słowy z obszaru „sztuka” zostaną pobrane tylko ilości, które powinny być pobierane w jednostka miary „sztuka” (czyli ilości mniejsze niż całe pudełko). Jeśli wystąpi niedobór w obszarze „pudełko”, można pobrać maksymalną możliwą liczbę pudełek w granicach łącznego popytu. Pozostałe ilości zostaną następnie pobrane z obszaru „sztuka”.

## <a name="where-it-applies"></a>Zastosowanie

Funkcja natychmiastowego uzupełniania zapasów jest używana podczas wykonywania grupy czynności, jeżeli alokacja nie powiedzie się dla wiersza dyrektywy lokalizacji, dla której jest ustawiony szablon uzupełnienia zapasów.

## <a name="set-up-immediate-replenishment"></a>Konfigurowanie natychmiastowego uzupełniania zapasów

- Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Dyrektywy lokalizacji**, a następnie na karcie **Wiersze** na liście **Szablon natychmiastowego uzupełniania zapasów** wybierz szablon uzupełnienia zapasów dla popytu grupy czynności.

Szablon uzupełniania zapasów zostanie zastosowany, jeśli wiersz dyrektywy lokalizacji nie przydzieli w ustawionej jednostce miary.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

Jeśli funkcja natychmiastowego uzupełniania zapasów jest wybrana dla wiersza dyrektywy lokalizacji, ale żadna praca uzupełniania zapasów nie zostanie wygenerowana podczas korzystania z szablonów uzupełniania zapasów popytu dla tego wiersza dyrektywy lokalizacji, należy zbadać dwie możliwe główne przyczyny:

- Upewnij się, że zastosowany szablon uzupełnienia zapasów popytu jest skonfigurowany tak, aby używał poprawnych szablonów lokalizacji i szablonów pracy typu **Uzupełnianie zapasów**.
- Upewnij się, że jest wystarczająca ilość dostępnych zapasów w lokalizacjach, gdzie szablon uzupełniania zapasów popytu szuka dostępnych zapasów dla uzupełnienia.
