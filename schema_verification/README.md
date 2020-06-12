In order to ensure that you have correctly installed the libraries to use MLSpecLib in this directory:

IN THE ROOT DIRECTORY:
```
pipenv shell
pipenv install
cd schema_verification
python3 test_schema.py
```

Field types currently supported:
    "string": fields.Str(),
    "uuid": fields.UUID(),
    "uri": fields.Str(validate=MLSchemaValidators.validate_type_URI),
    "datetime": MLSchemaFields.DateTime(),
    "semver": fields.Str(validate=MLSchemaValidators.validate_type_semver),
    "allowed_schema_types": fields.Str(),
    "boolean": fields.Boolean(),
    "list": fields.List(fields.Raw()),
    "list_strings": fields.List(
        fields.Str(validate=MLSchemaValidators.validate_type_string_cast)
    ),
    "list_of_tensor_shapes": fields.List(
        fields.Tuple([fields.Str(), fields.List(fields.Int)])
    ),
    "list_interfaces": fields.List(
        fields.Dict(validate=MLSchemaValidators.validate_type_interfaces)
    ),
    "workflow_steps": fields.Dict(
        validate=MLSchemaValidators.validate_type_workflow_steps
    ),
    "tags": fields.List(fields.Tuple([fields.Str(), fields.Str()])),
    "path": fields.Str(validate=MLSchemaValidators.validate_type_path),
    "dict": fields.Dict(),
    "float": fields.Float(),
    "email": fields.Email(),
    "bucket": fields.Str(validate=MLSchemaValidators.validate_type_bucket),
    "int": fields.Int(),