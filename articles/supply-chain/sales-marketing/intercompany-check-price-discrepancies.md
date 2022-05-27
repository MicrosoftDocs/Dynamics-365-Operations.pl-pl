---
title: Sprawdź rozbieżności ceny zamówienia międzyfirmowego
description: W tym temacie opisano sposób sprawdzania rozbieżności cen w zamówieniach międzyfirmowych
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3167077e653f2316f5ce54c2a07ef9c2978ecebb
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678326"
---
# <a name="check-intercompany-order-price-discrepancies"></a>Sprawdź rozbieżności ceny zamówienia międzyfirmowego

[!include [banner](../../includes/banner.md)]

Niniejsza procedura umożliwia sprawdzanie występowania rozbieżności cen na zamówieniach międzyfirmowych.

1. Przejdź do **Zaopatrzenie i sourcing \> Okresowe \> Czyszczenie \> Sprawdź rozbieżności ceny zamówienia międzyfirmowego**.
1. Skonfiguruj zadanie wsadowe w razie potrzeby, a następnie kliknij przycisk **OK**, aby sprawdzić ceny i rabaty dotyczące międzyfirmowych zamówień sprzedaży i zakupu, W przeciwnym przypadku wybierz przycisk **Anuluj**, aby zamknąć stronę bez sprawdzania.

    > [!TIP]
    > Jeśli wystąpią jakiekolwiek problemy z synchronizacją lub cenami, zostaną one wymienione w wyświetlonym komunikacie informacyjnym. Możesz wydrukować wiadomość informacyjną w celach informacyjnych.

1. W komunikacie informacyjnym wybierz odpowiedni wiersz, aby otworzyć zamówienie w bieżącym podmiocie prawnym. Otwórz zamówienie w powiązanej firmie, wybierając opcję **Międzyfirmowe**, a następnie **międzyfirmowe zamówienie zakupu** lub **międzyfirmowe zamówienie sprzedaży**.

    > [!NOTE]
    > Aby zezwolić na aktualizację zamówienia międzyfirmowego:
    >
    > 1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
    > 1. W okienku akcji wybierz kartę **Ogólne**, a następnie ponownie wybierz opcję **Międzyfirmowe**.
    > 1. Na stronie **Międzyfirmowe** wybierz **zasady zamówienia zakupu** lub **zamówienia sprzedaży**.
    > 1. Zaznacz **opcję Zezwalaj na edycję ceny** i **Zezwalaj na edycję rabatu** w obu obszarach.

1. Otwórz odpowiednie zamówienie międzyfirmowe, w którym chcesz zachować cenę.
1. Dla każdego wiersza zamówienia zmień wartość wiersza **Cena jednostki**, a następnie przywróć jego wartość oryginalną. Zmień i przywróć wartość pola **Rabat** w wierszu oraz zmień i przywróć wartości pól **Opłaty związane z zakupami** lub **Opłaty od sprzedaży**. Zmiana wartości tam iz powrotem spowoduje synchronizację cen, rabatów i opłat z tego wiersza zamówienia międzyfirmowego do wiersza zamówienia międzyfirmowego, do którego się odwołuje, dzięki czemu zostaną one automatycznie wyrównane.

    > [!NOTE]
    > Ta synchronizacja jest ważna tylko wtedy, gdy międzyfirmowe zamówienie sprzedaży nie zostało zafakturowane. Jeśli międzyfirmowe zamówienie sprzedaży zostało zaksięgowane na fakturze i utworzono arkusz faktur odbiorcy, zmiany należy wprowadzić bezpośrednio w wierszach międzyfirmowego zamówienia zakupu, ustawiając ceny, rabaty i opłaty równe tym w międzyfirmowym arkuszu faktur odbiorcy. Jeśli nie zostanie to zrobione, międzyfirmowe zamówienie zakupu nie może zostać zaksięgowane na fakturze, ponieważ będzie niezgodność w sumach zamówienia.

1. Powtarzaj procedurę, aż wszystkie międzyfirmowe zamówienia zakupu i sprzedaży zostaną zsynchronizowane.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
