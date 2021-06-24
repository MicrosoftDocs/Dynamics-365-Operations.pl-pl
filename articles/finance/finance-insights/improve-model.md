---
title: Usprawnij model przewidywania (wersja zapoznawcza)
description: W tym temacie opisano funkcje, których można używać w celu poprawy działania modeli przewidywania.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 184a1cb5d3851e26b41340b711c51ef38e06eb53
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186649"
---
# <a name="improve-the-prediction-model-preview"></a>Usprawnij model przewidywania (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano funkcje, których można używać w celu poprawy działania modeli przewidywania. Rozpoczynanie ulepszania modelu zaczyna się w obszarze roboczym **Prognozy płatności odbiorcy** w rozwiązaniu Microsoft Dynamics 365 Finance. Następnie czynności ulepszające wykonuje się w aplikacji AI Builder.

## <a name="select-historical-outcomes"></a>Wybór wyników historycznych

Najpierw wybierz co najmniej jeden z trzech możliwych wyników dla faktur: **Na czas**, **Opóźnione** i **Bardzo opóźnione**. Należy wybrać wszystkie trzy wyniki. Jeśli wyczyścisz wybór któregokolwiek z tych wyników, faktury zostaną odfiltrowane z procesu trenowania, a dokładność przewidywania spadnie.

[![Potwierdzanie wyników](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Jeśli organizacja wymaga tylko dwóch wyników, zmień wartości progowe wyników **Opóźnione** i **Bardzo opóźnione** na 0 (zero) dni. W ten sposób w praktyce zwijasz prognozę do stanu binarnego **Na czas** lub **Opóźnione**.

## <a name="select-fields"></a>Wybierz pola

Wybierając pola, które mają być uwzględnione w modelu, należy pamiętać, że lista zawiera wszystkie pola dostępne w tabeli usługi Microsoft Dataverse, które są mapowane na dane w Azure data lake. Niektóre z tych pól **nie powinny** być zaznaczane. Pola, których nie należy zaznaczać, należą do jednej z trzech kategorii:

- Pole jest wymagane przez tabelę usługi Dataverse, ale w data lake nie ma dla niej żadnych danych.
- Pole jest identyfikatorem i w związku z tym jest nieprzydatne dla funkcji uczenia maszynowego.
- Pole reprezentuje informacje, które nie będą dostępne podczas przewidywania.

W poniższych sekcjach przedstawiono pola dostępne dla jednostek faktury i odbiorcy oraz listę pól, które **nie powinny** być wybierane do trenowania. Kategoria określona dla każdego z tych pól nawiązuje do kategorii z poprzedzającej listy.
 
### <a name="invoice-dataverse-table"></a>Tabela Faktura Dataverse

Na poniższej ilustracji pokazano pola dostępne dla tabali Faktura.

[![Pola dostępne dla tabeli Faktura](./media/available-fields.png)](./media/available-fields.png)

Następujących pól nie należy wybierać do trenowania:

- **Konto faktury** (kategoria 2)
- **Zamknięte** (kategoria 3) — to pole służy do filtrowania faktur dla trenowania (zamknięte) i przewidywania (niezamknięte).
- **Nazwa** (kategoria 1)
- **Identyfikator źródła** (kategoria 2)
- **Rekord źródłowy** (kategoria 2)
- **Tabela źródłowa** (kategoria 2)

### <a name="customer-dataverse-table"></a>Tabela odbiorców Dataverse

Na poniższej ilustracji pokazano pola dostępne dla tabeli Odbiorca.

[![Pola dostępne dla tabeli Odbiorca](./media/related-entities.png)](./media/related-entities.png)

Następującego pola nie należy wybierać do trenowania:

- **Unikatowy klucz wiersza** (kategoria 2)

## <a name="filters"></a>Filtry

Filtry obecnie nie obsługują scenariusza prognozowania płatności od odbiorców. W związku z tym wybierz opcję **Pomiń ten krok** i przejdź do strony podsumowania.

[![Koncentrowanie modelu za pomocą filtrów](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
