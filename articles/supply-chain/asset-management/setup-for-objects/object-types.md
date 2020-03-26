---
title: Typy składnika majątku
description: W tym temacie wyjaśniono, jak tworzyć typy składników majątku w Zarządzaniu składnikami majątku. Opisano również elementy, które są związane z typami składników majątku.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a19b8c40dd7d48b2d78723c4411f1699819c4026
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124481"
---
# <a name="asset-types"></a>Typy składników majątku

[!include [banner](../../includes/banner.md)]



W tym temacie wyjaśniono, jak utworzyć typy składników majątku. Opisano również elementy, które są związane z typami składników majątku. Typy składników majątku są używane jako kategorie ogólne dla składników majątku. Przykładami są maszyny CNC, aparatura pomiarowa i silniki samochodowe. Typy składników majątku są używane do zarządzania typami zadań konserwacyjnych (zadania konserwacyjne), stanami cyklu życia składników majątku, licznikami, atrybutami składników majątku, szablonem oceny warunków i modelami składników majątku, które można wybrać dla składnika majątku. Podczas tworzenia składnika majątku należy określić jego typ.

Dla każdego typu składnika majątku można utworzyć odmiany ustawień typu. Na przykład jeśli masz typ składnika majątku o nazwie **Ciężarówki**, możesz utworzyć odmiany tego typu dla różnych producentów i modeli. Do każdego typu składnika majątku można dodać wymagane części zamienne i plany konserwacji.

Najpierw należy skonfigurować wymagane typy składników majątku. Następnie należy utworzyć modele składników majątku, które powinny być powiązane z typami składników majątku. Na koniec na stronie **Ustawienia domyślne typu składnika majątku** można utworzyć wszystkie odmiany typów składnika majątku, które są wymagane dla danego sprzętu.

## <a name="create-an-asset-type"></a>Tworzenie typu składnika majątku

1. Wybierz **Zarządzanie składnikami majątku** > **Ustawienia** > **Typy składników majątku** > **Typy składników majątku**.
2. Wybierz **Nowy**, aby utworzyć typ składnika majątku.
3. W polu **Typ składnika majątku** wprowadź identyfikator typu składnika majątku.
4. W polu **Nazwa** wprowadź nazwę.
5. W polu **Model cyklu życia składnika majątku** wybierz model cyklu życia składnika majątku. Aby uzyskać więcej informacji na temat stanów i modeli cyklu życia składnika majątku, zobacz temat [Stany cyklu życia składnika majątku](object-stages.md).
6. Ustaw opcję **Suma** na **Tak**, jeśli podsumowane wartości kluczowego wskaźnika wydajności (KPI) powinny być obliczane dla składników majątku, które mają ten typ składnika majątku.
7. Wybierz opcję **Zapisz**.
8. Na skróconej karcie **typy zadań konserwacji** wybierz typy zadań konserwacji, które powinny być powiązane z typem składnika majątku:

    - Aby wybrać typ zadania konserwacji, zaznacz go w polu **Pozostałe typy zadań konserwacji**, a następnie wybierz przycisk strzałki w prawo ![Przycisk strzałki w prawo](media/29-setup-for-objects.png), aby przenieść go do sekcji **Wybrane typy zadań konserwacji**.
    - Aby wybrać wszystkie dostępne typy zadań konserwacji, wybierz ![przycisk strzałki do przodu](media/30-setup-for-objects.png). Wszystkie typy zadań konserwacji są przenoszone z pola **Pozostałe typy zadań konserwacji** do pola **Wybrane typy zadań konserwacji**.
    - Aby anulować wybór typu zadania konserwacyjnego, wybierz je w polu **Wybrane typy zadań konserwacyjnych**, a następnie wybierz przycisk strzałki w lewo ![Przycisk strzałki w lewo](media/31-setup-for-objects.png), aby przenieść je do pola **Pozostałe typy zadań konserwacyjnych**.

9. Można również wybrać liczniki składnika majątku, które powinny być powiązane z typem składnika majątku. Na karcie skróconej **Liczniki** dokonaj wyborów przy użyciu metod, które są opisane dla typów zadań konserwacyjnych w kroku 8. Aby uzyskać więcej informacji o konfiguracji liczników, zobacz temat [Liczniki](counters.md).
10. Można również wybrać typy atrybutów, które powinny być powiązane z typem składnika majątku. Na karcie skróconej **Typy atrybutów** dokonaj wyborów przy użyciu metod, które są opisane dla typów zadań konserwacyjnych w kroku 8. Następnie, aby utworzyć preferowaną sekwencję typów atrybutów, wybierz typ atrybutu w polu **Wybrane typy atrybutów** i użyj strzałek w górę i w dół, aby je przenieść. Sekwencja typów atrybutów będzie wyświetlana w składnikach majątku, które używają tego typu składnika majątku. Aby uzyskać więcej informacji o atrybutach składników majątku, zobacz temat [Typy atrybutów konserwacji](../setup-for-functional-locations/specification-types.md).

    > [!NOTE]
    > Po dodaniu nowych typów atrybutów na karcie skróconej **Typy atrybutów** istniejące składniki majątku są automatycznie aktualizowane o te informacje.

11. Można również wybrać szablony oceny warunku, które powinny być powiązane z typem składnika majątku. Na karcie skróconej **Oceny warunku** dokonaj wyborów przy użyciu metod, które są opisane dla typów zadań konserwacyjnych w kroku 8. Aby uzyskać więcej informacji na temat szablonów oceny warunków i rejestracji, zobacz temat [Oceny warunku](../setup-for-objects/condition-assessment.md).
12. Na skróconej karcie **Model składnika majątku** wyświetlane są wszystkie kombinacje producentów i modeli składników majątku, które są skonfigurowane dla wybranego typu składnika majątku. Aby zobaczyć kombinacje podzielone według producenta, wybierz **Model składnika majątku**, aby otworzyć stronę **Model składnika majątku**.

    Na stronie **Model składnika majątku** można dodać relacje model-typ składnika majątku. Ponadto na stronie **Typy składnika majątku** można dodać relacje producent-model składnika majątku bezpośrednio do typu składnika majątku. Wreszcie na stronie **Model składnika majątku** (**Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Model składnika majątku**) może utworzyć nowe relacje producent-model-typ składnika majątku. W związku z tym istnieją trzy sposoby konfigurowania i edytowania relacji producent-model-typ składnika majątku. Wszystkie dostępne kombinacje są wyświetlane z różnych perspektyw i można wybrać preferowany punkt wejścia podczas pracy z konfiguracją.

> [!NOTE]
> - Jeśli wybrano liczniki typu środka trwałego, wybory zostaną automatycznie zaktualizowane na stronie **Liczniki** (**Zarządzanie składnikami majątku** > **Konfiguracja** > **Składniki majątku** > **Typy składników majątku** > **Liczniki**).
> - Pola w sekcji **Szczegóły** na skróconej karcie **Ogólne** pokazują liczbę typów zadań konserwacji, liczników, atrybutów itd., które są skonfigurowane dla wybranego typu składnika majątku.

Zazwyczaj zlecenia pracy, które są tworzone ręcznie, są związane z konserwacją korygującą, podczas gdy zlecenia pracy, które są tworzone automatycznie, są związane z konserwacją zapobiegawczą. Podczas ręcznego tworzenia zleceń pracy, można użyć tylko typy zadań konserwacji, które są zaznaczone na stronie skróconej karcie **Typy zadań konserwacji** na stronie **Typy składników majątku**. Jednak automatycznie utworzone zlecenia pracy mogą używać wszystkich typów zadań konserwacji tworzonych na stronie **Typy zadań konserwacji** (**Zarządzanie składnikami majątku** \> **Ustawienia** \> **Zadania** \> **Typy zadań konserwacji**).

## <a name="create-asset-type-setup-lines"></a>Tworzenie wierszy konfiguracji typu składnika majątku

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Typy składników majątku** \> **Konfiguracja typu składnika majątku**. Alternatywnie wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składniki majątku** \> **Typy składników majątku** \> **Typy składników majątku**, wybierz typ składnika majątku, a następnie opcję **Konfiguracja typu składnika majątku**.
2. Przy pierwszym użyciu strony **Konfiguracja typu składnika majątku** przydatny bywa przycisk **Utwórz kombinacje**. Za pomocą tego przycisku można szybko utworzyć wszystkie kombinacje modelu składnika majątku w danym typie. Wybierz opcję **Utwórz kombinacje**, wybierz typ składnika majątku, dla którego chcesz utworzyć kombinację, a następnie wybierz **OK**.

    > [!NOTE]
    > Jeśli nie będziesz używać wszystkich kombinacji ustawień typu składnika majątku, które zostały automatycznie utworzone, możesz usunąć konfigurację, zaznaczając ją, a następnie wybierając polecenie **Usuń**.

3. Wybierz opcję **Nowa**, aby ręcznie utworzyć konfigurację typu składnika majątku.
4. W zależności od tego, jak szczegółowa powinna być konfiguracja typu składnika majątku, dokonaj odpowiednich wyborów w polach **Typ składnika majątku**, **Producent** oraz **Model**.
5. Jeśli umowa gwarancyjna jest powiązana z typem składnika majątku, wybierz umowę w polach **Gwarancja dostawcy**oraz **Gwarancja klienta**. 
6. Na skróconej karcie **Części zamienne** wybierz **Dodaj**, aby dodać części zamienne do wybranego ustawienia typu składnika majątku.
7. Aby zatwierdzić część zamienną, wybierz wiersz części zamiennych, a następnie wybierz **Zatwierdź**. Można wybrać wiele wierszy do zatwierdzenia.
8. Aby sprawdzić, czy część zamienna jest używana w innym miejscu w module Zarządzanie składnikami majątku (na przykład w odniesieniu do składników majątku i zleceń pracy), wybierz wiersz części zamiennych, a następnie wybierz **Używająca pozycja**, aby otworzyć stronę **Używająca pozycja**. Aby wyświetlić wszystkie aktywne części zamienne na liście, zaznacz pole wyboru **Aktywne**. Aby wyświetlić tylko zatwierdzone części zamienne, należy zaznaczyć pole wyboru **Zatwierdzone**.
9. Na skróconej karcie **Plany konserwacji** wybierz opcję **Dodaj**, aby dodać plany konserwacji do wybranego ustawienia typu składnika majątku.
10. Aby skopiować konfigurację typu składnika majątku do innej konfiguracji, można użyć funkcji Kopiuj. Wybierz konfigurację typu składnika majątku, do której chcesz skopiować konfigurację, wybierz opcję **Kopiuj konfigurację**i wybierz konfigurację typu składnika majątku, z której chcesz skopiować konfigurację. Ustawienia różnych opcji określają, ile informacji jest dołączonych. Po zakończeniu wybierz przycisk **OK**, aby skopiować konfigurację.

> [!NOTE]
> Jeśli masz wiele wierszy części zamiennych i planów konserwacji, które będą używane ponownie, funkcja Kopiuj umożliwia szybkie i łatwe konfigurowanie danych dla wielu kombinacji ustawień typu składnika majątku.

## <a name="spare-parts-on-the-asset-type-setup"></a>Części zamienne w konfiguracji typu składnika majątku

Zgodnie z opisem w sekcji „Tworzenie wierszy ustawień typu składnika majątku” części zamienne są skonfigurowane na modelach składników majątku na stronie **Konfiguracja typu składnika majątku**. Dlatego po otwarciu strony **Konfiguracja typu składnika majątku** widać tylko te części zamienne, które są powiązane z wybraną kombinacją typu, producenta i modelu składnika majątku. Aby wyświetlić listę wszystkich rekordów części zamiennych, otwórz stronę **Części zmienne** (**Zarządzanie składnikami majątku** \> **Informacje** \> **Części zamienne**).

Na stronie **Części zamienne** można również tworzyć nowe części zamienne dla istniejących kombinacji typu, producenta i modelu składnika majątku. Można zdecydować, czy chce się utworzyć rekordy części zamiennych na stronie **Konfiguracja typu składnika majątku** lub na stronie **Części zamienne**. Strona **Konfiguracja typu składnika majątku** zapewnia omówienie danych dotyczących wybranej kombinacji typu, producenta i modelu składnika majątku, podczas gdy strona **Części zamienne** zawiera pełny przegląd wszystkich wierszy ustawień typu składnika majątku. Jeśli strona **Części zamienne** zawiera wiele rekordów, strona **Konfiguracja typu składnika majątku** może dawać lepszy przegląd.

Aby sprawdzić, czy część zamienna w wybranym wierszu jest używana gdziekolwiek indziej w module Zarządzanie składnikami majątku (na przykład w odniesieniu do składników majątku i zleceń pracy), wybierz **Używająca pozycja**, aby otworzyć stronę **Używająca pozycja**. 

