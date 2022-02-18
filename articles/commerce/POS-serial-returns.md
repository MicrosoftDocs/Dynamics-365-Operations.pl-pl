---
title: Zwrot produktów oznaczonych numerami seryjnymi w punktach sprzedaży
description: W tym temacie opisano możliwości sprawdzania poprawności elementów seryjnych w ramach procesu zwrotu w aplikacji dla punktu sprzedaży Microsoft Dynamics 365 Commerce (POS).
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 179d66e19c7fa81d587ea920b1c71468ec070177d7e7e68e45c2b58da2f9f5af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716355"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a>Zwrot produktów oznaczonych numerami seryjnymi w punktach sprzedaży

[!include [banner](includes/banner.md)]

W tym temacie opisano możliwości sprawdzania poprawności elementów seryjnych w ramach procesu zwrotu w aplikacji dla punktu sprzedaży Microsoft Dynamics 365 Commerce (POS).

> [!NOTE]
> W wersji Commerce 10.0.20 i nowszych dostępna jest nowa funkcja, która nazywa się **Doświadczenie w przetwarzaniu zwrotów zunifikowanych w POS**. Aby korzystać z walidacji numeru seryjnego podczas przetwarzania zleceń zwrotu w POS, należy włączyć tę funkcję. Informacje o innych możliwościach, jakie zapewnia ta funkcja, gdy jest włączona, można znaleźć w sekcji [Tworzenie zwrotów w POS](POS-returns.md).
>
> Po włączeniu tej funkcji nie można jej wyłączyć.

## <a name="options-for-validating-serialized-returns"></a>Opcje sprawdzania poprawności serializowanych zwrotów

Gdy włączona jest funkcja **Doświadczenie w przetwarzaniu zwrotów zunifikowanych w POS**, organizacje mogą przeprowadzać walidację zwrotów przedmiotów oznaczonych numerami seryjnymi za pośrednictwem POS. Ta funkcja może ostrzegać użytkowników, jeśli numer seryjny, który jest zwracany, różni się od oryginalnego numeru seryjnego, który został sprzedany. W wersji Commerce 10.0.20 i nowszych komunikat, który otrzymują użytkownicy jest tylko komunikatem ostrzegawczym. Użytkownicy mogą nadal przetwarzać zwroty na podstawie numeru seryjnego, który różni się od numeru seryjnego, który został pierwotnie sprzedany.

Aby skonfigurować sprawdzanie poprawności numeru seryjnego dla organizacji po włączeniu funkcji **Doświadczenie w przetwarzaniu zwrotów zunifikowanych w POS** , przejdź do sekcji **Handel detaliczny i komercyjny \> Konfiguracja centrali \> Parametry \> Parametry Commerce** w centrali Commerce. Na karcie **Zapasy** na skróconej karcie **Operacje magazynowe sklepu** ustaw wartość **Tak** dla opcji **Włącz weryfikację numerów seryjnych w aplikacji POS**.

## <a name="process-returns-for-serialized-items-in-pos"></a>Przetwarzanie zwrotów dla produktów serializowanych w POS

Jeśli opcja **Zezwalaj na sprawdzanie poprawności numerów seryjnych przy zwrotach z punktu sprzedaży** została ustawiona na **Tak**, to w przypadku zwrotu przez punkt sprzedaży elementu z numerem seryjnym użytkownik może wprowadzić numer seryjny dla linii zwrotu w okienku szczegółów na **Produkty zwrotne**. Jeśli numer seryjny, który jest wprowadzony nie pasuje do oryginalnego numeru seryjnego, który został sprzedany dla transakcji sprzedaży, użytkownik otrzymuje komunikat ostrzegawczy. Aplikacja nie uniemożliwia jednak użytkownikowi kontynuowania wysyłania zwrotu.

> [!NOTE]
> Obecnie POS obsługuje walidację numerów seryjnych tylko w przypadku linii zwrotnych, w których pierwotnie zamówiona ilość jest nie większa niż jeden. Jeśli oryginalny wiersz zamówienia sprzedaży został utworzony w kanale innym niż POS i jeśli ilość, która została zamówiona dla serializowanej pozycji na danej linii sprzedaży jest większa niż jeden, pozycja nie może zostać poprawnie zwrócona przez POS.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie zwrotów w POS](POS-returns.md)