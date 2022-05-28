---
title: Usprawnij model przewidywania
description: W tym temacie opisano funkcje, których można używać w celu poprawy działania modeli przewidywania.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 96ba1653ea1f9a5ac1037e9ecc7e85c86a6f31c7
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2022
ms.locfileid: "8719979"
---
# <a name="improve-the-prediction-model"></a>Usprawnij model przewidywania

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, których można używać w celu poprawy działania modeli przewidywania. Rozpoczynanie ulepszania modelu zaczyna się w obszarze roboczym **Prognozy płatności odbiorcy** w rozwiązaniu Microsoft Dynamics 365 Finance. Następnie czynności ulepszające wykonuje się w aplikacji AI Builder.

## <a name="select-historical-outcomes"></a>Wybór wyników historycznych

Najpierw wybierz co najmniej jeden z trzech możliwych wyników dla faktur: **Na czas**, **Opóźnione** i **Bardzo opóźnione**. Należy wybrać wszystkie trzy wyniki. Jeśli wyczyścisz wybór któregokolwiek z tych wyników, faktury zostaną odfiltrowane z procesu trenowania, a dokładność przewidywania spadnie.

[![Potwierdzanie wyników.](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

Jeśli organizacja wymaga tylko dwóch wyników, zmień wartości progowe wyników **Opóźnione** i **Bardzo opóźnione** na 0 (zero) dni. W ten sposób w praktyce zwijasz prognozę do stanu binarnego **Na czas** lub **Opóźnione**.

## <a name="select-fields"></a>Wybierz pola

Wybierając pola, które mają być uwzględnione w modelu, należy pamiętać, że lista zawiera wszystkie pola dostępne w tabeli usługi Microsoft Dataverse, które są mapowane na dane w Azure data lake. Niektóre z tych pól **nie powinny** być zaznaczane. Pola, których nie należy zaznaczać, należą do jednej z trzech kategorii:

- Pole jest wymagane przez tabelę usługi Dataverse, ale w data lake nie ma dla niej żadnych danych.
- Pole jest identyfikatorem i w związku z tym jest nieprzydatne dla funkcji uczenia maszynowego.
- Pole reprezentuje informacje, które nie będą dostępne podczas przewidywania.

W poniższych sekcjach przedstawiono pola dostępne dla jednostek faktury i odbiorcy oraz listę pól, które **nie powinny** być wybierane do trenowania. Kategoria określona dla każdego z tych pól nawiązuje do kategorii z poprzedzającej listy.
 
### <a name="invoice-dataverse-table"></a>Tabela Faktura Dataverse

Na poniższej ilustracji pokazano pola dostępne dla tabali Faktura.

[![Pola dostępne dla tabeli Faktura.](./media/available-fields.png)](./media/available-fields.png)

Następujących pól nie należy wybierać do trenowania:

- **Konto faktury** (kategoria 2)
- **Zamknięte** (kategoria 3) — to pole służy do filtrowania faktur dla trenowania (zamknięte) i przewidywania (niezamknięte).
- **Nazwa** (kategoria 1)
- **Identyfikator źródła** (kategoria 2)
- **Rekord źródłowy** (kategoria 2)
- **Tabela źródłowa** (kategoria 2)

### <a name="customer-dataverse-table"></a>Tabela odbiorców Dataverse

Na poniższej ilustracji pokazano pola dostępne dla tabeli Odbiorca.

[![Pola dostępne dla tabeli Odbiorca.](./media/related-entities.png)](./media/related-entities.png)

Następującego pola nie należy wybierać do trenowania:

- **Unikatowy klucz wiersza** (kategoria 2)

## <a name="filters"></a>Filtry

Faktury używane do szkolenia można filtrować, ustawiając kryteria filtrowania pól na fakturze lub w tabelach odbiorców. Na przykład można ustawić próg, aby uwzględnić tylko faktury, których suma jest równa lub przekracza określoną kwotę. Alternatywnie można wykluczyć faktury skojarzone z odbiorcami w określonej grupie odbiorców.

Aby uzyskać więcej informacji na temat filtrowania danych, zobacz [Tworzenie modelu prognozowania](/ai-builder/prediction-create-model#filter-your-data).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
