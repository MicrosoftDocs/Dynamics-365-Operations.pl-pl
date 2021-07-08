---
title: Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary
description: Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f3ebd47ffc85d4ca257b404579d60d679f7929b6
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301312"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary

Kod błędu: LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:

> Niektóre towary wymagane w ładunku %1 nie zostały jeszcze pobrane i przeniesione do końcowej lokalizacji wysyłki.

W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.

## <a name="cause"></a>Powód

Nie można potwierdzić ładunku lub wysyłki w jego bieżącym stanie, ponieważ może istnieć jeden z następujących warunków:

- Powiązana praca nie została jeszcze pobrana i przeniesiona do końcowej lokalizacji wysyłki.
- Ilość pobrania pracy nie odpowiada utworzonej ilości pracy w wierszu ładunku.
- Dyrektywa lokalizacji została skonfigurowana z lokalizacją pakowania jako ostateczną lokalizacją wysyłki podczas korzystania z konteneryzacji szablonu grup czynności.

## <a name="resolution"></a>Rozwiązanie

Ładunek lub wysyłka jest obecnie w stanie, w którym potwierdzenie wysyłki nie powiedzie się. Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:

- Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.
- Anuluj identyfikatory robocze, które zostały utworzone z lokalizacją pakowania jako ostateczną lokalizacją wysyłki, skonfiguruj ponownie dyrektywę lokalizacyjną i ponownie zwolnij ładunek.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają

Poniższa procedura służy do przeglądu linii ładunkowych i upewnienia się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.
1. Zanotuj wartość pola **Ilość stworzonych prac**.
1. W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.
1. Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.
1. Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a>Anuluj identyfikatory robocze, które zostały utworzone z lokalizacją pakowania jako ostateczną lokalizacją wysyłki, skonfiguruj ponownie dyrektywę lokalizacyjną i ponownie zwolnij ładunek

Użyj poniższej procedury, aby anulować identyfikatory pracy, które mają lokalizację pakowania jako ostateczną lokalizację odkładania z uruchomioną automatyczną konteneryzacją.

1. Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.
1. Zostanie otwarte okno dialogowe **Anuluj pracę**. W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować. Wybrany identyfikator pracy musi mieć **Status pracy** o wartości *Otwarta*, *W toku*, *Kanałowa*, *Połączona* lub *Zamknięta*.
1. Kliknij przycisk **OK**.
1. Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.
1. W razie potrzeby powtórz tę procedurę dla innych identyfikatorów roboczych.

Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).

Korzystając z poniższej procedury, należy ponownie skonfigurować dyrektywę lokalizacji, tak aby nie używała lokalizacji pakowania jako ostatecznej lokalizacji wysyłki, gdy dla szablonu grup czynności zostanie ustawiona automatyczna konteneryzacja.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Dyrektywy lokalizacji**.
1. W polu **Typ zlecenia pracy** wybierz opcję *Zamówienia sprzedaży*.
1. Wybierz dyrektywę lokalizacji, której używasz do automatycznej konteneryzacji.
1. Na skróconej karcie **Działania w ramach dyrektywy lokalizacyjnej** wybierz pozycję **Edytuj kwerendę**.
1. W oknie dialogowym edytora zapytań, na zakładce **Zakres** znajdź wiersz, w którym **Pole** jest ustawione na *Profil lokalizacji* i sprawdź, czy pole **Kryteria** dla tego wiersza nie jest ustawione na profil lokalizacji, który ma **Typ lokalizacji** o wartości *Pakowanie*. Dostosuj pole **Kryteria**, aby skorygować końcową lokalizację odłożeń.

Użyj poniższej procedury, aby ponownie zwolnić ładunek i utworzyć identyfikatory robocze z prawidłową ostateczną lokalizacją wysyłki.

1. Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.
1. W sekcji **Ładunki** znajdź ładunek, który musi zostać zwolniony.
1. Na pasku narzędzi sekcji **Ładunki** wybierz opcję **Zwolnij \> Zwolnij do magazynu**, aby zwolnić wybrany ładunek do magazynu.
1. W razie potrzeby powtórz tę procedurę dla innych ładunków.
