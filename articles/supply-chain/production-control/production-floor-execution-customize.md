---
title: Dostosowanie interfejsu wykonania hal produkcyjnych
description: W tym temacie wyjaśniono sposób rozszerzania bieżących formularzy oraz tworzenia nowych formularzy i przycisków dla interfejsu wykonywania produkcji.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 67fb381cbef6f1673afcaa834666b4a859bdf4e6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066553"
---
# <a name="customize-the-production-floor-execution-interface"></a>Dostosowanie interfejsu wykonania hal produkcyjnych

[!include [banner](../includes/banner.md)]

Deweloperzy mogą rozszerzać obecne formularze lub tworzyć własne formularze i przyciski dla interfejsu wykonawczego hali produkcyjnej. Po dodaniu kodu dla tych nowych elementów administratorzy lub kierownicy produkcji mogą w prosty sposób dodawać je do interfejsu przy użyciu standardowych formantów konfiguracji.

Oto na przykład niektóre z możliwych rozwiązań, jeśli w głównym formularzu są potrzebne nowe kolumny:

- Rozszerz formularz `JmgProductionFloorExecutionMainGrid` i dodaj żądane pola.
- Utwórz nowy formularz i dodaj go jako nowy główny widok (karta).

## <a name="add-a-new-button-action"></a>Dodaj nowy przycisk (akcja)

Aby dodać nowy przycisk (akcja), wykonaj następujące kroki, aby utworzyć klasę implementującą niestandardową akcję.

1. Utwórz nową klasę o nazwie `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`, gdzie:

    - `<ExtensionPrefix>` jednoznacznie identyfikuje rozwiązanie, zazwyczaj używając nazwy firmy.
    - `<ActionName>` to unikalna nazwa klasy. Zwykle określa rodzaj akcji.

1. Nowa klasa musi rozszerzać klasę `JmgProductionFloorExecutionAction`.
1. Zastąp wszystkie niezbędne metody.

Na przykład kod należy sprawdzić dla następujących klas:

- `JmgProductionFloorExecutionBreakAction` — klasa prostej akcji, która nie wymaga żadnych rekordów.
- `JmgProductionFloorExecutionReportFeedbackAction` — klasa udostępnia bardziej złożoną funkcjonalność.

Po zakończeniu pracy nowy przycisk (akcja) będzie automatycznie wymieniony na karcie **Projekt** w Microsoft Dynamics 365 Supply Chain Management. Można tam (albo administrator, kierownik ds. aplikacji) w prosty sposób dodać go do głównego lub pomocniczego paska narzędzi, tak jak można dodać standardowe przyciski. Aby uzyskać więcej informacji, zobacz [Projektowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-tabs.md).

## <a name="add-a-new-main-view"></a>Dodawanie nowego widoku głównego

1. Utwórz nowy formularz, który ma żądane elementy i funkcje. Należy zauważyć, że ten formularz jest nowym formularzem, a nie rozszerzeniem. Nazwa formularza `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`, w którym:

    - `<ExtensionPrefix>` jednoznacznie identyfikuje rozwiązanie, zazwyczaj używając nazwy firmy.
    - `<FormName>` to unikalna nazwa formularza.

1. Utwórz element menu o nazwie `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`.
1. Utwórz rozszerzenie o nazwie `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, gdzie metoda `getMainMenuItemsList` jest rozszerzona przez dodanie nowego elementu menu do listy. Poniższy kod przedstawia przykład.

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionForm))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

Po zakończeniu pracy nowy widok główny będzie automatycznie wymieniony w polu kombi **Widoku głównego** na karcie **Projekt** w sekcji Supply Chain Management. Tam Ty (lub administrator lub kierownik piętra) możesz łatwo dodać go do nowych lub istniejących kart, tak jak możesz dodać standardowe widoki główne. Aby uzyskać więcej informacji, zobacz [Projektowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-tabs.md).

## <a name="add-a-details-view"></a>Dodaj widok szczegółów

1. Utwórz nowy formularz, który ma żądane elementy i funkcje. Pamiętaj, że ten formularz jest nowy, a nie rozszerzenie. Nazwa formularza `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`, w którym: 

    - `<ExtensionPrefix>` jednoznacznie identyfikuje rozwiązanie, zazwyczaj używając nazwy firmy.
    - `<FormName>` to unikalna nazwa formularza.

1. Utwórz element menu o nazwie `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`.
1. Utwórz rozszerzenie o nazwie `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, gdzie metoda `getDetailsMenuItemList` jest rozszerzona przez dodanie nowego elementu menu do listy.

Po zakończeniu pracy nowy widok szczegółów będzie automatycznie wymieniony w polu kombi **Widoku szczegółów** na karcie **Projekt** w sekcji Supply Chain Management. Tam Ty (lub administrator lub kierownik piętra) możesz łatwo dodać go do nowych lub istniejących kart, tak jak możesz dodać standardowe widoki szczegółów. Aby uzyskać więcej informacji, zobacz [Projektowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-tabs.md).

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>Dodawanie klawiatury numerycznej do formularza lub okna dialogowego

W poniższym przykładzie pokazano sposób dodawania klawiatur numerycznych do formularza.

1. Liczba kontrolerów klawiatury numerycznej, które zawierają każdy formularz, musi być równa liczbie klawiatur numerycznych w tym formularzu.

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. Skonfiguruj zachowanie każdego kontrolera klawiatury numerycznej i połącz każdy kontroler klawiatury numerycznej z elementami formularza klawiatury numerycznej.

    ```xpp
    /// <summary>
    /// Initializes all numpad controllers, defines their behavior and connects them with numpad form parts.
    /// </summary>
    public void initializeNumpadController()
    {
        numpadController1 = new JmgProductionFloorExecutionNumpadController();
        numpadController1.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_1);
        QuantityNumpad1.getPartFormRun().setNumpadController(numpadController1);
    
        numpadController2 = new JmgProductionFloorExecutionNumpadController();
        numpadController2.parmNumpadEnabled(false);
        numpadController2.parmNumpadValue(333.56);
        numpadController2.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_2);
        QuantityNumpad2.getPartFormRun().setNumpadController(numpadController2);
    }
    ```

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>Użyj klawiatury numerycznej jako okna dialogowego okna podręcznego

W poniższym przykładzie pokazano jeden sposób skonfigurowania kontrolera klawiatury numerycznej dla okna podręcznego.

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

Poniższy przykład pokazuje jeden ze sposobów wywołania wyskakującego okna dialogowego klawiatury numerycznej.

```xpp
Args args = new Args();
args.name(formstr(JmgProductionFloorExecutionNumpad));
args.menuItemName(menuItemDisplayStr(JmgProductionFloorExecutionNumpad));
args.caller(element);
Object formRun = classfactory.formRunClass(args);
formRun.init();
formRun.setNumpadController(numpadController);
numpadController.setValueToNumpad(333.56);
formRun.run();
```

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Stylizacja interfejsu wykonania hal produkcyjnych](production-floor-execution-styles.md)
- [Projektowanie interfejsu wykonania hal produkcyjnych](production-floor-execution-tabs.md)
