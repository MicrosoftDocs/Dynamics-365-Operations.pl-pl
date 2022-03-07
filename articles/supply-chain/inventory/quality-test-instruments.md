---
title: Przyrządy testowe zarządzania jakością
description: W tym temacie opisano sposób tworzenia przyrządów testowych, których można używać w testach w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39624a9f00829e551fe3790a024155b6104318ef5cc1c582ab263c3868462063
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774109"
---
# <a name="quality-management-test-instruments"></a>Przyrządy testowe zarządzania jakością

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia przyrządów testowych, których można używać w testach w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.

Strona **Przyrządy testowe** umożliwia definiowanie i wyświetlanie szczegółów dotyczących urządzeń używanych do wykonywania testów w zleceniach kontroli jakości. Przyrządy testowe są opcjonalne. Mogą jednak pomóc pracownikom kontroli jakości zorientować się, którego urządzenia lub narzędzia powinni używać do wykonania określonego testu.

## <a name="test-instrument-example"></a>Przykład przyrządu testowego

Wykonujesz różne testy na elementach elektrycznych. Niektóre testy dotyczą napięcia tych elementów, jeden test dotyczy temperatury, a jeden test dotyczy masy. Do wykonania każdego z tych testów są używane różne narzędzia, urządzenia lub sprzęt. Na przykład woltomierz służy do pomiaru napięcia, termometr do pomiaru temperatury, a waga do pomiaru masy. Każde z tych urządzeń można skonfigurować jako przyrząd testowy i wskazać jednostkę miary, w której mają być rejestrowane wyniki testu. Na przykład wyniki z woltomierza są rejestrowane w woltach, wyniki z termometru są rejestrowane w stopniach Fahrenheita lub Celsjusza, a wyniki z wagi są rejestrowane w funtach lub kilogramach.

## <a name="create-a-test-instrument"></a>Tworzenie przyrządu testowego

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Przyrządy testowe**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Przyrząd testowy** – wpisz unikatowy identyfikator lub nazwę przyrządu testowego.
    - **Opis** – wprowadź szczegółowy opis przyrządu testowego.
    - **Jednostka** — umożliwia wybranie jednostki miary przyrządu. Pole **Dokładność** jest ustawiane automatycznie na podstawie wybranej jednostki.

1. Zamknij stronę.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Test zarządzania jakością](quality-tests.md)
- [Grupy testowe zarządzania jakością](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
