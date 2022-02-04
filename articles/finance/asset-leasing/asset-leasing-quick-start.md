---
# required metadata
title: Wynajem składnika majątku — rozpoczęcie
description: W tym temacie opisano możliwości wynajmu składników majątku i kroki tworzenia wynajmu składników majątku i wyświetlania informacji dotyczących tych wynajmów.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: null
ms.technology: null
ms.search.form: AssetLeaseLeasingWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: '2020-09-24'
ms.dyn365.ops.version: 10.0.14
---

# <a name="asset-leasing-get-started"></a>Wynajem składnika majątku — rozpoczęcie

[!include [banner](../includes/banner.md)]

W tym temacie opisano możliwości wynajmu składników majątku i kroki tworzenia wynajmu składników majątku i wyświetlania informacji dotyczących tych wynajmów. W tym temacie opisano również terminologię używaną w interfejsie użytkownika i w dokumentacji. Wynajem składnika majątku jest zaawansowaną funkcją służącą do zarządzania, śledzenia i automatyzowania transakcji finansowych wynajmowanych składników majątku w Microsoft Dynamics 365 Finance. Wynajem składników majątku jest zgodny z międzynarodowymi standardami rachunkowości (MSSF 16) i standardami finansowymi (ASC 842). Wynajem składników aktywów wyszukuje i przetwarza informacje o dzierżawie oraz ułatwia generowanie wpisy w arkuszu w cyklu wynajmu od początkowego rozpoznania, miesięcznych wpisów w arkuszu, do utraty ważności zakończenia wynajmu. Wynajem składników majątku integruje się płynnie z innymi komponentami Dynamics 365 Finance, w tym Środkami trwałymi, Rozrachunki z dostawcami i Księga główna.

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego **Zarządzanie funkcjami**, aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. W obszarze roboczym **Zarządzanie funkcjami** znajdź i wybierz funkcję o nazwie **Wynajem składnika majątku**, a następnie wybierz przycisk **Włącz teraz**.

Aby uzyskać więcej informacji dotyczących standardów księgowania, zapoznaj się z dokumentacją standardową dla MSSF 16 i US ASC 842.

## <a name="asset-leasing-elements"></a>Elementy leasingu składnika majątku
Na poniższym schemacie przedstawiono główne elementy procesu biznesowego dotyczącego wynajmu.

[![Elementy leasingu składnika majątku.](./media/overview-01.png)](./media/overview-01.png)

Wynajęty składnik majątku zawiera następujące główne składniki:

- **Umowa wynajmu** — najmodawca jest właścicielem składnika aktywów i zgadza wynająć najemcy składnik majątku w wybranym okresie w zamian za okresowe opłaty z tytułu wynajmu. Oprócz umowy prawnej między najmodawcą a najemcą umowa najmu zawiera decyzje dotyczące zarządzania, takie jak prawdopodobieństwo użycia opcji odnowienia i przeniesienia własności.

- **Obliczanie i klasyfikacja wynajmu według standardu księgowego** — obliczanie i klasyfikacja wynajmu identyfikuje standard rachunkowości, który będzie stosowany w początkowej i późniejszej wymiarze, a także test klasyfikacji określający jaki będzie typ wynajmu. Wynajem może być leasingiem finansowym, leasingiem operacyjnym, dzierżawą krótkoterminową lub wynajmem o niskiej wartości. System oblicza również wartość netto bieżącą przyszłych opłat z tytułu wynajmu w celu wyceny i klasyfikacji.

- **Transakcje wynajmu** — wynajem składnika majątku umożliwia początkowe uznawanie składnika majątku z prawem do użytkowania do leasingu w bilansie, a także dalszych miar w leasingu w bilansie lub poza bilansem. Początkowa transakcja uznania mierzy bieżącą wartość netto przyszłych opłat z tytułu wynajmu. Te dane służą do określenia wartości początkowego składnika majątku z prawem do użytkowania i zobowiązania z tytułu wynajmu, które ma wpływ na bilans organizacji. Kolejne miary miesięcznej transakcji wynajmu obejmują kumulację odsetek za zobowiązanie z tytułu wynajmu, które zwiększa zobowiązanie z tytułu wynajmu. Mierzy również naliczenie opłaty z tytułu wynajmu, które zmniejszają zobowiązanie z tytułu wynajmu, a które następnie zostaną wypłacone najmodawcy. Miara obejmuje także amortyzację składnika majątku z prawem do użytkowania.

  W przypadku wynajmu poza bilansem system oblicza wydatki na wynajem liniowy w zależności od tego, który z nich jest krótszy: ekonomiczny okres użytkowania składnika aktywów lub okres wynajmu. Korekty wynajmu mierzą modyfikacje umowy, takie jak wydłużenie lub rozszerzenie wynajmu transakcje utraty wartości, w których używane są składniki majątku z prawem do użytkowania w odniesieniu do kosztów nie do odzyskania.

  Wynajem składnika majątku jest integrowany z księgą główną w celu zapewnienia, że wszystkie zaksięgowane transakcje wynajmu zaktualizują plan kont. Wynajem składnika majątku jest integrowany jest integrowany z rozrachunkami z dostawcami w celu śledzenia faktur najmodawcy w rozrachunkach z dostawcami i obsługuje przyszłe płatności. Integracja ze środkami trwałymi pozwala śledzić dzierżawy w rejestrze środków trwałych i księgować składniki majątku z prawem do użytkowania, w tym wstępne uznanie, amortyzację i utratę wartości środka trwałego, z poziomu środków trwałych.   

## <a name="asset-leasing-components"></a>Komponenty wynajmu składnika majątku 
Wynajem składnika majątku mapuje informacje o wynajmie, harmonogramy płatności, daty rozpoczęcia i zakończenia oraz częstotliwość płatności. Automatyzuje również obliczenia dotyczące wartości netto obecnej, miesięcznej opłaty z tytułu wynajmu, odsetek i amortyzacji wynajmu. W zależności od konfiguracji system wykonuje testy klasyfikacji wynajmu. System tworzy także i księguje odpowiednie transakcje leasingu, które są oparte na systemie zdefiniowanym przez stosowany standard rachunkowy.

Na poniższym schemacie przedstawiono księgę wynajmu, wynajem, obliczony harmonogram płatności, testy klasyfikacji wynajmu i ksiąg wynajmu oraz odpowiadające im transakcje księgowania.

[![Wynajem, księga wynajmu i harmonogram płatności.](./media/overview-02.png)](./media/overview-02.png)

- **Księga wynajmu** — zawiera wszystkie informacje o umowach leasingowych, takie jak warunki wynajmu, wartość godziwa i opłaty z tytułu wynajmu. Zawiera także stosowany standard rachunkowy, typ wynajmu oraz progi, które są brane pod uwagę w teście klasyfikacji wynajmu. Księga wynajmu zawiera także transakcje wynajmu zaksięgowane w księdze głównej. 
  
- **Wynajem** — wynajem zawiera informacje o wynajmie składnika aktywów, które reprezentują podstawę wynajmu składnika aktywów, źródło informacji o wynajmie to umowa wynajmu i decyzja dotycząca zarządzania, które są wykonywane poza systemem Dynamics 365 Finance. Wartość godziwa środka trwałego to cena, która zostałaby zapłaconą za środek trwały w transakcji w dniu miary. Ta wartość może zależeć od typu składnika aktywów, warunków rynkowych i innych kryteriów, które mogą być brane pod uwagę w ocenie. Wartość godziwa środka trwałego będzie uwzględniana w równaniu testowym klasyfikacji.

- **Okres użyteczności środków trwałych** — oznacza pozostałe okresy użyteczności środka trwałego, od daty rozpoczęcia wynajmu. Okres użyteczności środka trwałego będzie uwzględniany w równaniu testowym klasyfikacji. Różni się ona od okresu użyteczności zdefiniowanego w środkach trwałych.

- **Krańcowa stopa procentowa** — to jest stopa procentowa, która zostanie użyta do obliczenia wartości netto obecnej. System użyje stawki niejawnej, jeśli jest zdefiniowana w danych wynajmu w celu obliczenia wartości netto bieżącej opłaty z tytułu wynajmu. Jeśli niejawna stawka nie jest zdefiniowana, system będzie używał krańcowej stopy procentowej.

- **Typ annuity** — jest to opłata z tytułu wynajmu należna albo na początku okresu płatności, albo na koniec okresu. Może to być płatność zaliczkowa lub annuita należna (na początku okresu opłaty z tytułu wynajmu) lub zwykłą annuita (na koniec okresu opłaty z tytułu wynajmu).

  Pierwszy miesiąc będzie traktowany jako numer okresu zero dla płatności z góry pierwszy miesiąc będzie traktowany jako okres jeden dla zaległości w płatnościach.

- **Interwał łączenia** — reprezentuje liczbę okresów łączenia odsetek na rok. Może to być comiesięcznie (12 okresów rocznie), kwartalnie (4 okresy rocznie), pół roku (2 okresy na rok) lub rocznie (1 okres na rok). Liczba okresów zostanie uwzględniona w obliczeniu wartości netto obecnej.

- **Data rozpoczęcia** — jest to data, z którą najmodawca udostępnia składnik aktywów do użycia przez najemcę. Wszystkie obliczenia i transakcje dotyczące wynajmu będą oparte na dacie rozpoczęcia. Data rozpoczęcia powinna przypadać na początku okresu (pierwszy dzień miesiąca), aby zapewnić dokładność kolejnych obliczeń. Można użyć pola **Data podpisu umowy** do wprowadzenia daty rzeczywistej, kiedy umowa została podpisana.

- **Okres wynajmu** — to jest długość okresu wynajmu (w miesiącach).

> [!NOTE] 
> Definicja okresu wynajmu zależy od liczby okresów (lub interwałów) w wierszach harmonogramu płatności. Zdefiniowana liczba interwałów zostanie przeliczona na miesiące.

- **Wiersz harmonogramu płatności** — zawiera opłaty z tytułu wynajmu w danym okresie. Określa również, czy okres odnawiania jest wykonywany i włączony do początkowej miary składnik majątku z prawem do użytkowania i zobowiązania z tytułu wynajmu. Można zdefiniować datę początkową płatności leasingowych oraz interwały okresu, które reprezentują długość wynajmu, np. dni, miesiące lub lata.

- **Częstotliwość płatności** — wskazuje, czy płatność jest miesięczna, kwartalna, półroczna czy coroczna. Data końcowa jest obliczana automatycznie na podstawie daty rozpoczęcia i liczby wprowadzonych okresów.

- **Harmonogram płatności** — jest to obliczona wartość netto bieżąca na podstawie długości okresu objętego opłatami z tytułu wynajmu, kwotą płatności, okresów łączenia oraz typu annuity.

- **Okresy** — są to okresy wynajmu odpowiadające interwałowi łączenia i typowi annuity. Interwał łączenia określa sposób podziału okresów. Można skonfigurować następujące interwały łączenia:

  - Miesięczne, 12 okresów na rok
  - Kwartalne, 4 okresy na rok
  - Półroczne, 2 okresy na rok
  - Roczne, 1 okres na rok

Pierwszy okres rozpoczyna się od okresu zero, jeśli typem annuity jest annuita należna. W przeciwnym wypadku pierwszy okres rozpoczyna się od okresu jeden, jeśli typem annuity są zaległości w płatnościach.

- **Miesiące** — wskazuje liczbę miesięcy kalendarzowych w okresie trwania wynajmu. Kwota płatności to kwota należna zgodnie z definicją w częstotliwości płatności. Obliczona wartość netto bieżąca to opłata netto z tytułu wynajmu oparta na wartości bieżącej dla okresu, interwałach łączenia oraz krańcowej stopie procentowej.

> [!NOTE] 
> Wartość netto bieżąca jest obliczana na podstawie rozliczonego równania przepływu gotówki.

- **Księgi** — są to wstępnie skonfigurowane ustawienia, które będą skojarzone z każdym wynajmem. Księga określa stosowany standard księgowania, typy wynajmu i próg używany jako podstawa dla testów klasyfikacji. Testy klasyfikacji służą do automatycznego określania typu wynajmu.

- **Struktura księgowa** — umożliwia wyświetlenie wybranego standardu rachunkowego, MSSF 16 i ASC 842, który jest obsługiwany. Standard rachunkowy jest wyznaczany na podstawie księgi skojarzonej z danym wynajmem. Standard rachunkowy określa konta księgi określone w profilu księgowania.

- **Typy wynajmu** — wskazuje, które z dwóch typów wynajmu będą używane: leasing finansowy lub leasing operacyjny. W ramach leasingu finansowego ryzyko i korzyści związane z wynajętym składnikiem majątku są przenoszone do najemcę. W ramach leasingu operacyjnego ryzyko i korzyści związane z wynajętym składnikiem majątku pozostają u najmodawcy. Trzecia opcja jest zautomatyzowaną identyfikacją typu wynajmu, finansowego lub operacyjnego, na podstawie zdefiniowanych progów w księdze. Ta automatyczna identyfikacja jest wykonywana podczas testu przeklasyfikowania wynajmu.

- **Progi** — ta opcja jest używana w testach klasyfikacji leasingu w celu określenia, czy składnik aktywów został sklasyfikowany jako jeden z następujących elementów:

  - **Okres wynajmu** — jest to wartość procentowa okresu użyteczności, który ma być używany w teście klasyfikacji. System klasyfikuje wynajem jako finansowy, jeśli typ wynajmu jest ustawiany automatycznie i jeśli okres wynajmu w okresie użyteczności środka trwałego, jest większy lub równy wartości procentowej określonej w tym polu.

  - **Wartość bieżąca netto** — jest to wartość procentowa wartości godziwej składnika majątku, która ma być używana w teście klasyfikacji. System klasyfikuje wynajem jako finansowy, jeśli typ wynajmu jest ustawiany automatycznie i jeśli wartość netto bieżąca przyszłych opłat z tytułu wynajmu w okresie użyteczności środka trwałego jest większa lub równy wartości procentowej określonej w tym polu.

  - **Wynajem krótkoterminowy** — jeśli okres wynajmu jest mniejszy lub równy zdefiniowanej wartości, wynajem zostanie zaklasyfikowany jako krótkoterminowy.

  - **Niska wartość** — jeśli wartość godziwa składnika majątku jest mniejszy lub równy zdefiniowanej wartości, wynajem zostanie zaklasyfikowany jako wynajem o niskiej wartości.

  - **Klasyfikacja wynajmu i transakcje** Klasyfikacja wynajmu jest procesem automatycznym, który umożliwia klasyfikowanie wynajmów na podstawie określonych progów w księgach, oprócz innych kryteriów testowania klasyfikacji w celu określenia, czy leasing jest leasingiem finansowym, leasingiem operacyjnym, wynajmem krótkoterminowym czy wynajmem o niskiej wartości. Umożliwia to również określenie, czy stosowany jest proces odroczonego czynszu.

Do testów klasyfikacji należą Transfer własności, Opcja zakupu, Okres wynajmu, Obecna wartość netto i Unikatowy środek trwały. Na poniższym diagramie przedstawiono testy klasyfikacji wynajmu.

[![Testy klasyfikacji wynajmu.](./media/overview-03.png)](./media/overview-03.png)

Każdy typ wynajmu różnie obsługuje księgowanie w zależności od transakcji leasingowych. Transakcje obejmują początkowe uznanie, koszty odsetek, płatności z tytułu wynajmu i amortyzację leasingu i są oparte na stosowanych standardach księgowych (MSSF 16 lub ASC 842). Konta księgowe są definiowane w profilu księgowania wynajmu dla każdego typu transakcji i struktury księgowej.

## <a name="asset-leasing-transactions"></a>Wynajem składnika majątku — transakcje

#### <a name="initial-recognition"></a>Początkowe rozpoznawanie 
Podczas początkowego uznawania wynajętego składnika majątku używana jest obliczona wartość obecna netto, co może być zgłaszane w bilansie. Odpowiedni wpis księgowy jest generowany automatycznie. Ta transakcja obciąża rachunek składnika majątku z prawem do użytkowania i uznaje rachunek zobowiązania leasingu operacyjnego w następujący sposób: Jeśli środek trwały jest skojarzony z wynajmem, wpis początkowego uznania zostanie określony jako nabycie środka trwałego. W tym scenariuszu należy zdefiniować profil księgowania środków trwałych, który będzie księgowany na koncie składnika majątku z prawem do użytkowania. 

> [!NOTE]
> Leasing operacyjny jest obsługiwany tylko przez US GAAP ASC 842.

|     Typ                                          |     Uznanie                     |     Strona kredytowa                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Leasing operacyjny w ramach US GAAP            |     Składnik majątku z prawem do użytkowania        |     Zobowiązanie z tytułu leasingu operacyjnego     |
|     Leasing finansowy według MSSF i US GAAP      |     Składnik majątku z prawem do użytkowania        |     Zobowiązanie z tytułu leasingu finansowego       |

#### <a name="lease-liability-amortization-interest-expense"></a>Amortyzacja zobowiązania z tytułu wynajmu (koszty odsetek) 
Odsetki dla wynajmu są uznawane przez obliczanie odsetek dla salda początkowego, okresu opłat z tytułu wynajmu, stopy procentowej odsetek oraz okresów złożonych w ciągu roku. Kwota odsetek zwiększa stan konta zobowiązanie z tytułu wynajmu operacyjnego przez jego uznanie, co będzie widoczny w bilansie organizacji. Transakcja obejmuje również zapis obciążenia na koncie kosztów odsetek, co jest uwzględnione w zestawieniu zysków i strat w leasingu finansowym oraz na koncie wydatków leasingowych dla leasingu operacyjnego.

|     Typ                                          |     Uznanie                     |     Środki                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Wpis zobowiązania z tytułu leasingu operacyjnego w ramach US GAAP ASC 842    |     Wydatek z tytułu wynajmu         |     Zobowiązanie z tytułu leasingu operacyjnego         |
|     Wpis zobowiązania z tytułu leasingu finansowego w ramach MSSF i US GAAP      |     Odsetki          |     Zobowiązanie z tytułu leasingu finansowego           |

#### <a name="accrued-lease-payment"></a>Naliczona opłata z tytułu wynajmu
Naliczona opłata z tytułu wynajmu jest uznawana za przyszłą płatność z tytułu wynajmu, która jest należna do przetworzenia jako transakcja płatności z konta bankowego lub kont kasowych. Należne płatności leasingowe zmniejszają zobowiązanie zobowiązanie z tytułu wynajmu przez obciążanie konta zobowiązania z tytułu wynajmu w księdze podrzędnej dostawy jeśli najmodawca jest określony jako dostawca lub zaksięgowania uznania w księdze not zobowiązań; następnie płatność zostanie przekazana do dostawcy lub not zobowiązań.

|     Typ                                          |     Uznanie                     |     Strona kredytowa                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Leasing operacyjny w ramach US GAAP              |  Zobowiązanie z tytułu leasingu operacyjnego    |   Zobowiązanie wobec dostawcy (księga podrzędna)/Noty zobowiązań  |
|     Leasing finansowy według MSSF i US GAAP        |  Zobowiązanie z tytułu leasingu finansowego      |   Zobowiązanie wobec dostawcy (księga podrzędna)/Noty zobowiązań  |

#### <a name="asset-depreciation"></a>Amortyzacja składnika majątku
Składnik majątku z prawem do użytkowania jest amortyzowany w zależności od tego, co jest krótsze — okres użyteczności składnika majątku czy okres leasingu. Metoda obliczania amortyzacji dla leasingu operacyjnego US GAAP (ASC 842) jest oparta na różnicy między liniowymi wydatkami na wynajem a kwotą odsetek. Wycofanie leasingu finansowego są obliczane za pomocą standardowej metody liniowej. Amortyzacja wynajmu ma wpływ na zestawienie zysków i strat dzięki obciążeniu kosztami odsetek. Bilans jest zmieniany przez uznanie narastającego rachunku składnik majątku z prawem do użytkowania w leasingu finansowym. Jeśli wynajem jest połączony z środkiem trwałym, transakcje amortyzacji będą wykonywane tylko z modułu środków trwałych. 

|     Typ                                          |     Uznanie                     |     Strona kredytowa                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Leasing operacyjny w ramach US GAAP              |  Wydatek z tytułu wynajmu                |   Wartość umorzenia składnika majątku z prawem do użytkowania     |
|     Leasing finansowy według MSSF i US GAAP        |   Amortyzacja wydatków składnika majątku z prawem do użytkowania   |   Wartość umorzenia składnika majątku z prawem do użytkowania    |

#### <a name="short-term-lease"></a>Wynajem krótkoterminowy
Leasing krótkoterminowy jest uznawany za wydatek, który wpłynie na zestawienie przychodów w organizacji. Wytworzona należna opłata z tytułu wynajmu obciąży konto wydatków wynajmu i uzna noty zobowiązań lub konto księgi podrzędnej dostawcy.

|     Typ                                          |     Uznanie                     |     Strona kredytowa                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Wpis wynajmu krótkoterminowego według MSSF i US GAAP     |  Wydatek z tytułu wynajmu                |   Zobowiązanie wobec dostawcy (księga podrzędna)/Noty zobowiązań  |

#### <a name="low-value-lease"></a>Wynajem o niskiej wartości
Wynajem o niskiej wartości jest uznawany za wydatek, który wpłynie na zestawienie przychodów w organizacji. Wytworzona należna opłata z tytułu wynajmu obciąży wydatki wynajmu i uzna noty zobowiązań lub konto księgi podrzędnej dostawcy.

|     Typ                                          |     Uznanie                     |     Strona kredytowa                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Wpis wynajmu o niskiej wartości według MSSF i US GAAP      |  Wydatek z tytułu wynajmu                |   Zobowiązanie wobec dostawcy (księga podrzędna)/Noty zobowiązań  |


#### <a name="index-revaluation"></a>Przeszacowanie indeksu
Jest to konto leasingu środków trwałych dla zmiennych opłat z tytułu wynajmu mierzonych według stawki indeksowanej. Zmiany w opłatach z tytułu wynajmu spowodowane przez wahania stawki indeksowanej stanowią korektę leasingową na podstawie MSSF 16. Zobowiązanie z tytułu wynajmu i składniki majątku z prawem do użytkowania zostaną skorygowane na rachunku nowych płatności. 

|     Typ                                          |     Uznanie                             |     Strona kredytowa                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Wpis przeszacowania wskaźnika zgodnie z MSSF w przypadku zwiększenia  |  Składnik majątku z prawem do użytkowania       |   Zobowiązanie z tytułu leasingu operacyjnego |
|   Wpis przeszacowania wskaźnika zgodnie z MSSF w przypadku zmniejszenia  |  Zobowiązanie z tytułu leasingu operacyjnego  |   Składnik majątku z prawem do użytkowania      |

Gdy płatności ulegną zmianie ze względu na zmianę stawki indeksowanej, tylko opłaty zmienne ulegną zmianie, o ile nie istnieją dodatkowe zmiany w przepływach środków pieniężnych, takie jak zmiana warunków leasingu związanych z oprocentowaniem w ramach US GAAP ASC 842.

#### <a name="lease-adjustment"></a>Korekta wynajmu
Leasing składnika aktywów pozwala na skorygowanie wynajmu w przypadku zmodyfikowania warunków leasingu, przedłużenia wynajmu lub jeśli istnieją dodatkowe okoliczności, w których wynajem wymaga korekty. Korekty wynajmu są księgowane w celu zwiększenia lub zmniejszenia składnika majątku z prawem do użytkowania i zobowiązania z tytułu wynajmu. W procesie korekty następuje przeniesienie sald końcowego umorzenia zobowiązań i salda aktywów w dniu korekty. Jeśli dzierżawa jest połączona z środkiem trwałym, korekta składnika majątku z prawem do użytkowania zostanie zaksięgowana przy użyciu identyfikatora przypisanego w środkach trwałych. 

|     Typ                                          |     Uznanie                             |     Strona kredytowa                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Wpis korekty wynajmu dla MSSF i US GAAP w przypadku zwiększenia     |  Składnik majątku z prawem do użytkowania       |   Zobowiązanie z tytułu leasingu operacyjnego |
|   Wpis korekty wynajmu dla MSSF i US GAAP w przypadku zmniejszenia     |  Zobowiązanie z tytułu leasingu operacyjnego  |   Składnik majątku z prawem do użytkowania      |


#### <a name="lease-impairment"></a>Utrata wartości wynajmu
Oznacza przeniesienie zmniejszenia salda składnika majątku z prawem do użytkowania. Określ kwotę utraty wartości, datę transakcji i pozostałe okresy. Pozostały składnik majątku z prawem do użytkowania z będzie amortyzowany liniowo. Logika utraty wartości wynajmu uwzględnia wartość przeniesienia środka trwałego, która istnieje w planie amortyzacji środków trwałych.  

|     Typ                                          |     Uznanie                             |     Strona kredytowa                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Wpis utraty wartości dla MSSF i US GAAP           |  Wydatek utraty wartości                   |    Składnik majątku z prawem do użytkowania     |

>[!NOTE]
> Jeśli wynajem jest połączony ze środkiem trwałym, należy zaksięgować utratę wartości wynajmu ze środków trwałych, ponieważ amortyzacja środków trwałych jest uruchamiana z modułu Środki trwałe.

**Dwie waluty** Transakcje dzierżawy mogą być księgowane w walucie innej niż waluta księgowania i waluta raportowania. Kurs wymiany waluty jest definiowany w księdze głównej w dniu rozpoczęcia. Kursy wymiany można zmieniać, ustawiając pole **Stały kurs** na **Tak** podczas tworzenia wynajmu. Podczas wprowadzania transakcji wynajmu transakcje początkowego uznania i późniejszej amortyzacji użyją kursu wymiany na dzień rozpoczęcia okresu. W kolejnych transakcjach płatności i odsetek będzie używany bieżący aktywny kurs wymiany. 

## <a name="create-an-asset-lease"></a>Tworzenie wynajmu składnika majątku
Aby utworzyć nowy wynajem, należy wykonać następujące kroki. 

1. Aby korzystać z funkcji **Wynajem składnika majątku**, należy ją włączyć w obszarze roboczym **Zarządzanie funkcjami**. W obszarze roboczym **Zarządzanie funkcjami** wybierz opcję **Wszystkie**, aby wyświetlić na stronie wszystkie funkcje. Wybierz **Wynajem składnika majątku**, a następnie **Wyłącz teraz**.
2. Przejdź do **Wynajem składnika majątku >Wspólne > Podsumowanie wynajmu**. Na skróconej karcie **Ogólne** wprowadź wartość w wymaganych polach. 
   - **Szczegóły wynajmu**
   - **Okres użyteczności składnika majątku (w miesiącach)**
   - **Grupa wynajmu**
   - **Krańcowa stopa procentowa (%)**
   - **Interwał łączenia**
   - **Typ annuity**
   - **Waluta**
   - **Data rozpoczęcia**

3. Przejdź do skróconej karty **Wiersze harmonogramu płatności** i wprowadź wiersz płatności, a następnie wybierz opcję **Utwórz harmonogramy**.

4. Wybierz **Księgi**. 

5. Przełącz się na skróconą kartę **Ogólne**. Zostaną obliczone wartości **Początkowy składnik majątku z prawem do użytkowania** i **Zobowiązanie z tytułu wynajmu**. 

6. Przejdź do skróconej karty **Test klasyfikacji wynajmu**, aby sprawdzić wartość w **Typ wynajmu**. 

   Automatyczny **Typ wynajmu** jest klasyfikowany zgodnie z kryteriami zdefiniowanymi na stronie **Księgi**.

7.  Przejdź do obszaru **Harmonogram płatności** w sekcji **Funkcja**.  

   Na stronie **Harmonogram płatności** widoczne są przyszłe harmonogramy płatności dla identyfikatora wynajmu. Wybierz opcję **Potwierdź harmonogram**, aby móc zaksięgować transakcje **Początkowe uznanie**. 

[![Funkcja początkowego uznania.](./media/overview-13.png)](./media/overview-13.png)

8. Wybierz opcję **Początkowe uznanie**, aby utworzyć arkusz początkowego uznania. 

9. Wybierz opcję **Dzienniki wynajmu składnika majątku**, aby zaksięgować transakcję początkowego uznania. 

   Z poziomu harmonogramu płatności można otworzyć stronę szczegółową zawierającą transakcji składnika majątku z prawem do użytkowania. 
 
   **Harmonogram amortyzacji zobowiązań z tytułu wynajmu** pokazuje kwotę odsetek obliczoną dla każdego okresu.
   
10. Utwórz arkusz, a następnie przejdź do **Arkusze wynajmu składnika majątku**. **Harmonogram amortyzacji zobowiązań z tytułu wynajmu** jest także widoczny w przypadku transakcji odsetek.

   Na stronie **Harmonogram amortyzacji składników majątku** wyświetlane są transakcje amortyzacji dla wybranego identyfikatora wynajmu. 

   [![Strona transakcji składników majątku z PDU.](./media/overview-20.png)](./media/overview-20.png)

   Strona **Transakcje składników majątku z PDU** zawiera początkowe uznanie, wartość umorzenia i saldo składników majątku. 

   Na stronie **Transakcje zobowiązań z tytułu wynajmu** wyświetlane jest początkowe uznanie, płatność odsetek za wynajem, płatność za wynajem i saldo zobowiązania z tytułu wynajmu. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
