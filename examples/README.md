# Validating anydata subtree

1. Download install my fork of libyang https://github.com/ahassany/libyang/tree/anydata-strict-parsing 

2. validate a good message:
```bash
yanglint -t notif -Y lib.json -e -p models  models/ietf-yang-push@2019-09-09.yang example.json
```

3. validate an invalid message:
```bash
❯ yanglint -t notif -Y lib.json -e -p models  models/ietf-yang-push@2019-09-09.yang invalid-example.json
libyang err : Node "NOT_VALID_LIST_NAME" not found as a child of "interfaces" node. (Data location "/ietf-interfaces:interfaces", line number 14.)
YANGLINT[E]: Failed to parse input data file "invalid-example.json".
```