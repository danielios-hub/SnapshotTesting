# SnapshotTesting

A description of this package.

### Declare snapshot test in the setUp of every snapshot test class inserting name of the class 
and strategy

```
    override func setUp() {
        super.setUp()
        SnapshotTesting.insertIfNeeded(String(describing: PhoneViewSnapshotTests.self), strategy: .assert)
    }
```

### Create a test method and create snapshot tests
```
func test_initialLoad() {
    let (sut, _) = makeSUT()
    snapshotTest(snapshot: sut.snapshot(for: .iPhone13(style: .light)), named: "PHONEVIEW_INITIAL_LOAD_LIGHT")
    snapshotTest(snapshot: sut.snapshot(for: .iPhone13(style: .dark)), named: "PHONEVIEW_INITIAL_LOAD_DARK")
}
```
