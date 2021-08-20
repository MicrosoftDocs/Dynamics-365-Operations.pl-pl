---
title: Testy zarządzania jakością
description: W tym temacie opisano sposób tworzenia testów, których można używać w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62e5aca8c41aa324802e83e53f52ea39b623a65882962413e743e6dd2671a901
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781045"
---
# <a name="quality-management-tests"></a>Testy zarządzania jakością

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia testów, których można używać w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.

Strona **Testy** służy do definiowania i wyświetlania poszczególnych testów decydujących, czy produkty są zgodne ze specyfikacjami jakości. Do grupy testowej można przypisać jeden lub więcej testów. W takim przypadku określa się również informacje właściwe dla danego testu, takie jak akceptowalne wartości pomiaru. Wartości pomiarowe są używane w testach ilościowych. W przypadku testów jakościowych są używane zmienne testowe.

- W przypadku testów ilościowych pole **Typ** ma wartość *Liczba całkowita* lub *Ułamek*. Jest również określona jednostka miary. Specyfikacje jakości i wyniki testu są wyrażane jako liczby.
- W przypadku testów jakościowych w polu **Typ** jest ustawiona wartość *Opcja*. Testy jakości wymagają dodatkowych informacji konfiguracyjnych dotyczących zmiennej testowej i jej wyliczonych opcji. Specyfikacje jakości i wyniki testu są wyrażane jako liczby.

Opcjonalnie można przypisać przyrząd testowy do testu. Jednak przyrządy testowe nie są wymagane do tworzenia i używania testów ze zleceniami kontroli jakości. Aby uzyskać więcej informacji, zobacz temat [Przyrządy testowe zarządzania kontrolą jakości](quality-test-instruments.md).

Opcjonalnie można także określić jednostkę dla testu, aby wskazać jednostkę miary, w której są rejestrowane wyniki testu. Na przykład test temperatury może zawierać jednostkę stopni Fahrenheita lub stopni Celsjusza.

## <a name="example-of-a-test"></a>Przykładowy test

Firma produkcyjna wykonuje dwa testy na zakupionym materiale, w tym test ilości dotyczący jakości materiału i test jakości dotyczący uszkodzenia opakowania. Firma definiuje dodatkowe informacje na temat testu jakości w celu określenia zmiennej testowej (na przykład uszkodzone opakowanie) i jej wartości wynikowe. Firma używa strony **Grupy testowe** do przypisania dwóch testów do grupy testowej i do określenia informacji specyficznych dla testu. Grupa testów jest przypisywana do zlecenia kontroli jakości, dzięki czemu firma może raportować wyniki testu dla dwóch testów.

## <a name="create-a-test"></a>Tworzenie testu

Wykonaj poniższe kroki, aby utworzyć test.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Testy**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Test** – wpisz unikatowy identyfikator lub nazwę testu.
    - **Opis** – wprowadź szczegółowy opis testu.
    - **Typ** — Umożliwia wybór typu wyników testu. W przypadku testów ilościowych wybierz wartość *Ułamek* lub *Liczba całkowita*. W przypadku testów jakościowych wybierz opcję *Opcja*.
    - **Przyrząd testowy** — należy wybrać [przyrząd testowy](quality-test-instruments.md), który ma być używane w teście.
    - **Jednostka** — w przypadku wybrania w polu **Typ** wartości *Ułamek* lub *Liczba całkowita* (to jest, jeśli test jest testem ilościowym) należy wybrać jednostkę miary, w której mają być rejestrowane wyniki testu.

1. Zamknij stronę.

> [!NOTE]
> Po zapisaniu testu nie można już edytować pola **Typ** w siatce. Jeśli trzeba zmienić typ wyników testu, które będą rejestrowane dla testu, wybierz opcję **Zmień typ testu jakości** w okienku akcji. W oknie dialogowym **Zmień typ testu jakości** ustaw żądany typ w polu **Nowy typ**, a następnie wybierz przycisk **OK**, aby zamknąć okno dialogowe.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Przyrządy testowe zarządzania jakością](quality-test-instruments.md)
- [Grupy testowe zarządzania jakością](quality-test-groups.md)
- [Zmienne testu zarządzania jakością](quality-test-variables.md)
- [Powiązania jakości](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
