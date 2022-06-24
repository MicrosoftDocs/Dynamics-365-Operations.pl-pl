---
title: Dokumenty składnika majątku
description: W tym artykule objaśniono dokumenty w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectDocument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a2e8d72dc938c43e266c6b7c39329f827c56607a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899477"
---
# <a name="asset-documents"></a>Dokumenty składnika majątku

[!include [banner](../../includes/banner.md)]

 

W tym artykule objaśniono dokumenty w module Zarządzanie składnikami majątku.

W module Zarządzanie składnikami majątku można skonfigurować dokumenty w taki sposób, aby były one automatycznie powiązane na przykład z typami zadań, producentami składników majątku, typami składników majątku lub składnikami majątku. Ta funkcja jest przydatna, kiedy zwalniane są zaktualizowane wersje dokumentów. W takim przypadku wystarczy umieścić zaktualizowany dokument w standardowej lokalizacji, której używasz dla dokumentów Supply Chain Management, i dołączyć dokument do utworzonego rekordu dokumentu składnika majątku. Do zaktualizowanego dokument można następnie uzyskać dostęp z menu **Wszystkie składniki majątku**, **Aktywne składniki majątku**, **Moje aktywne składniki majątku**, **Wszystkie zlecenia pracy** oraz **Aktywne zadania zleceń pracy**. Proces dołączania dokumentów do rekordu dokumentu zasobów używa standardowego systemu obsługi dokumentów.

**Przykład 1:** dokument, który jest powiązany z typem zadania może opisywać procedurę dla tego typu zadania.

**Przykład 2:** dokument powiązany z kombinacją typu składnika majątku, producenta i modelu może być standardowym podręcznikiem dla wybranego modelu producenta składnika majątku.

## <a name="create-asset-document-relation"></a>Tworzenie relacji dokumentu składnika majątku

1. Wybierz kolejno **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Dokumenty składnika majątku**.
2. Wybierz **Nowy**, aby utworzyć rekord dokumentu składnika majątku.
3. W zależności od tego, jak szczegółowa ma być relacja dokumentu, dokonaj odpowiednich selekcji w jednym lub kilku z następujących pól: **Typ składnika majątku**, **Producent**, **Model**, **Składnik majątku**, **Kategoria typy zadania**, **Typ zadania**, **Wariant typu zadania** oraz **Kryterium doboru** Opcje, które są dostępne w polach **Wariant typu zadania** i **Kryterium doboru** zależą od opcji wybranych w polu **Typ zadania**.

    > [!NOTE]
    > Gdy system wyszukuje dokumenty, które powinny być powiązane ze składnikami majątku lub zleceniem pracy, moduł Zarządzanie składnikami majątku przechodzi przez wszystkie rekordy dokumentu składnika majątku w celu sprawdzenia możliwego dopasowania. W pierwszej kolejności sprawdza zawsze kombinację najbardziej szczegółową. Innymi słowy, moduł Zarządzanie składnikami majątku najpierw sprawdza dopasowanie dla pola **Kryterium doboru**. Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Wariant typu zadania**. Jeśli nie znaleziono dopasowania, sprawdza dopasowanie dla pola **Typ zadania** itd. Jak widać w układzie strony **Dokumenty składnika majątku** to zachowanie oznacza, że aby znaleźć najbardziej konkretną kombinację, moduł Zarządzanie składnikami majątku sprawdza każdy rekord od prawej do lewej pod kątem dopasowania. Kilka dokumentów może być związanych ze składnikiem majątku lub zleceniem pracy. Zależnie od potrzeb można edytować poziom usługi na żądaniu konserwacji lub zleceniu pracy.

4. Wybierz **Załączniki**. Zostanie wyświetlona standardowa strona **Obsługa dokumentów**.
5. Skonfiguruj dokumenty lub notatki, które powinny być dołączone do rekordu dokumentu składnika majątku. Po dołączeniu dokumentów w polu **Załączniki** pokazuje się liczba dokumentów powiązanych z rekordem.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]